import { useState, useEffect, useCallback } from "react";

const banks = ["Nubank", "Itaú", "Bradesco", "Caixa Econômica", "Inter", "Santander"];

const Index = () => {
  const [step, setStep] = useState(1);
  const [rangeVal, setRangeVal] = useState(2000);
  const [progress, setProgress] = useState(0);
  const [showError, setShowError] = useState(false);
  const [filaNum, setFilaNum] = useState(76);
  const [loaderText, setLoaderText] = useState("Analisando CPF...");

  const goTo = useCallback((s: number) => setStep(s), []);

  // Step 2: loader sequence
  useEffect(() => {
    if (step !== 2) return;
    const phrases = ["Verificando Score...", "Consultando Receita...", "Liberando Ofertas..."];
    let i = 0;
    const interval = setInterval(() => {
      setLoaderText(phrases[i]);
      i++;
      if (i === phrases.length) {
        clearInterval(interval);
        setTimeout(() => goTo(3), 1000);
      }
    }, 1500);
    return () => clearInterval(interval);
  }, [step, goTo]);

  // Step 7: progress bar
  useEffect(() => {
    if (step !== 7) return;
    setProgress(0);
    setShowError(false);
    let w = 0;
    const interval = setInterval(() => {
      if (w >= 99) {
        clearInterval(interval);
        setShowError(true);
      } else {
        w++;
        setProgress(w);
      }
    }, 50);
    return () => clearInterval(interval);
  }, [step]);

  // Step 8: fila countdown
  useEffect(() => {
    if (step !== 8) return;
    setFilaNum(76);
    const interval = setInterval(() => {
      setFilaNum((n) => (n <= 3 ? n : n - 1));
    }, 3000);
    return () => clearInterval(interval);
  }, [step]);

  const formatVal = (v: number) => v.toLocaleString("pt-BR");

  return (
    <div className="min-h-screen bg-background">
      {/* Step 1 */}
      {step === 1 && (
        <div className="animate-fade-in">
          <nav className="bg-gradient-cred p-6 text-primary-foreground text-center shadow-lg">
            <h1 className="font-mont font-black text-2xl tracking-tighter">
              CREDP<span className="text-secondary">IX</span>
            </h1>
            <p className="text-[10px] uppercase tracking-[3px] opacity-80">A solução financeira em 2 minutos</p>
          </nav>

          <div className="max-w-md mx-auto p-6">
            <div className="text-center my-8">
              <h2 className="font-mont font-black text-3xl text-foreground leading-tight italic">
                Dinheiro na conta via PIX em minutos.
              </h2>
              <p className="text-muted-foreground mt-2 font-bold">
                Liberação imediata para negativados e baixo score.
              </p>
            </div>

            <div className="bg-card rounded-[30px] p-8 shadow-2xl border border-border">
              <div className="space-y-4">
                <input type="text" placeholder="Nome Completo" className="w-full p-4 bg-muted border-2 border-border rounded-2xl focus:border-primary outline-none" />
                <input type="tel" placeholder="CPF" className="w-full p-4 bg-muted border-2 border-border rounded-2xl focus:border-primary outline-none" />
                <input type="date" className="w-full p-4 bg-muted border-2 border-border rounded-2xl focus:border-primary outline-none" />
                <button onClick={() => goTo(2)} className="w-full bg-secondary text-secondary-foreground font-black py-5 rounded-2xl shadow-lg uppercase font-mont transition-all active:scale-95">
                  Consultar Limite Grátis
                </button>
              </div>
            </div>

            <div className="mt-10 space-y-4">
              <p className="font-bold text-muted-foreground uppercase text-[10px] tracking-widest ml-2">Depoimentos Recentes</p>
              <div className="bg-card p-4 rounded-2xl shadow-sm border border-border flex gap-3">
                <div className="w-10 h-10 bg-primary/10 rounded-full flex items-center justify-center font-bold text-primary shrink-0">M</div>
                <div>
                  <p className="text-xs font-bold">Maria Auxiliadora</p>
                  <p className="text-[11px] text-muted-foreground">"Paguei o token de ativação e em 5 minutos o dinheiro tava na conta. Me salvou!"</p>
                </div>
              </div>
            </div>

            <footer className="mt-12 text-center text-[10px] text-muted-foreground pb-10">
              <p className="font-bold uppercase mb-2 text-foreground/60">CredPix Soluções Digitais LTDA</p>
              <p>Av. Brigadeiro Faria Lima, 3477 - Itaim Bibi, São Paulo - SP</p>
              <p>CNPJ: 44.650.594/0001-30 | Contato: (11) 4003-8921</p>
            </footer>
          </div>
        </div>
      )}

      {/* Step 2: Loading */}
      {step === 2 && (
        <div className="animate-fade-in bg-card flex flex-col items-center justify-center min-h-screen p-10 text-center">
          <div className="w-20 h-20 border-8 border-muted border-t-primary rounded-full animate-spin mb-8" />
          <h2 className="font-mont font-black text-xl text-foreground uppercase italic">{loaderText}</h2>
          <p className="text-muted-foreground text-sm mt-4">Aguarde, não feche esta página.</p>
        </div>
      )}

      {/* Step 3: Range */}
      {step === 3 && (
        <div className="animate-fade-in p-6">
          <div className="max-w-md mx-auto text-center mt-10">
            <h2 className="font-mont font-black text-2xl text-foreground italic uppercase">Limite Pré-Aprovado!</h2>
            <p className="text-muted-foreground text-sm mb-10">Arraste para selecionar o valor desejado:</p>
            <div className="bg-card p-10 rounded-4xl shadow-2xl border border-border">
              <p className="text-[10px] font-bold text-primary uppercase tracking-[3px] mb-2">Valor Escolhido:</p>
              <p className="text-5xl font-black text-foreground font-mont mb-8">R$ {formatVal(rangeVal)}</p>
              <input
                type="range" min={2000} max={10000} step={500} value={rangeVal}
                onChange={(e) => setRangeVal(Number(e.target.value))}
                className="w-full mb-10 accent-primary"
              />
              <button onClick={() => goTo(4)} className="w-full bg-primary text-primary-foreground font-black py-5 rounded-2xl shadow-lg uppercase font-mont">
                Confirmar Valor
              </button>
            </div>
          </div>
        </div>
      )}

      {/* Step 4: Plans */}
      {step === 4 && (
        <div className="animate-fade-in p-6">
          <div className="max-w-md mx-auto text-center mt-10">
            <h2 className="font-mont font-black text-2xl text-foreground italic uppercase">Plano de Pagamento</h2>
            <p className="text-muted-foreground text-sm mb-6 underline">Primeira parcela para daqui a 180 dias</p>
            <div className="grid gap-4">
              {[
                { parcelas: 36, valor: (rangeVal / 36).toFixed(2) },
                { parcelas: 48, valor: (rangeVal / 48).toFixed(2) },
                { parcelas: 64, valor: (rangeVal / 64).toFixed(2) },
              ].map((p) => (
                <button key={p.parcelas} onClick={() => goTo(5)} className="bg-card p-6 rounded-3xl border-2 border-border hover:border-primary text-left transition-all">
                  <p className="text-xs font-bold text-muted-foreground">{p.parcelas}x de</p>
                  <p className="text-2xl font-black text-foreground font-mont">R$ {p.valor}</p>
                </button>
              ))}
            </div>
          </div>
        </div>
      )}

      {/* Step 5: PIX info */}
      {step === 5 && (
        <div className="animate-fade-in p-6">
          <div className="max-w-md mx-auto bg-card p-8 rounded-4xl shadow-2xl mt-10">
            <h2 className="font-mont font-black text-xl mb-6 text-center uppercase italic">Onde quer receber?</h2>
            <div className="space-y-4">
              <input type="text" placeholder="Chave PIX (CPF, Celular ou Email)" className="w-full p-4 bg-muted border-2 border-border rounded-2xl outline-none" />
              <select className="w-full p-4 bg-muted border-2 border-border rounded-2xl outline-none">
                <option>Selecione seu Banco</option>
                {banks.map((b) => <option key={b}>{b}</option>)}
              </select>
              <input type="tel" placeholder="WhatsApp para envio do contrato" className="w-full p-4 bg-muted border-2 border-border rounded-2xl outline-none" />
              <button onClick={() => goTo(6)} className="w-full bg-primary text-primary-foreground font-black py-5 rounded-2xl shadow-lg uppercase font-mont mt-4">
                Gerar Contrato Digital
              </button>
            </div>
          </div>
        </div>
      )}

      {/* Step 6: Terms */}
      {step === 6 && (
        <div className="animate-fade-in p-6">
          <div className="max-w-md mx-auto bg-card p-8 rounded-4xl shadow-2xl mt-10">
            <h2 className="font-mont font-black text-xl mb-4 text-center">TERMO DE ADESÃO</h2>
            <div className="h-48 overflow-y-scroll bg-muted p-4 rounded-2xl text-[10px] text-muted-foreground leading-relaxed mb-6 border border-border">
              <p>1. O CredPix atua como integrador de crédito bancário...</p>
              <p>2. A liberação do saldo depende da validação do Token de Transferência...</p>
              <p>3. A taxa de ativação de R$ 27,00 é obrigatória para emissão do contrato...</p>
              <p>4. O valor da taxa será estornado ao cliente no primeiro resgate...</p>
              <p>5. Prazo de carência de 180 dias para a primeira parcela...</p>
              <p>6. O cliente autoriza a consulta ao Score de crédito...</p>
              <p>7. A transferência via PIX é realizada de forma imediata após a compensação da taxa...</p>
              <p>8. Cancelamentos podem ser feitos em até 7 dias...</p>
              <p>9. Fica eleito o foro de São Paulo para dirimir dúvidas...</p>
              <p>10. Ao clicar em aceito, você concorda com a emissão do Token de Saque.</p>
            </div>
            <button onClick={() => goTo(7)} className="w-full bg-success text-success-foreground font-black py-5 rounded-2xl shadow-lg uppercase font-mont">
              Li e Aceito os Termos
            </button>
          </div>
        </div>
      )}

      {/* Step 7: Progress */}
      {step === 7 && (
        <div className="animate-fade-in p-6">
          <div className="max-w-md mx-auto text-center mt-20">
            <h2 className="font-mont font-black text-xl text-foreground mb-8 uppercase italic">Enviando seu PIX...</h2>
            <div className="w-full bg-muted h-8 rounded-full overflow-hidden shadow-inner border-2 border-card">
              <div className="bg-success h-full transition-all duration-300" style={{ width: `${progress}%` }} />
            </div>
            <p className={`text-xs font-bold mt-4 uppercase tracking-[3px] ${showError ? "text-destructive" : "text-muted-foreground"}`}>
              {showError ? "ERRO NA TRANSFERÊNCIA (99%)" : `Enviando PIX (${progress}%)`}
            </p>

            {showError && (
              <div className="mt-10 bg-destructive/5 border-2 border-destructive/20 p-6 rounded-[30px] animate-bounce">
                <p className="text-destructive font-black font-mont text-lg uppercase italic mb-2">Transferência Bloqueada!</p>
                <p className="text-destructive/80 text-xs font-bold leading-relaxed mb-6">
                  Identificamos que seu Token de Ativação ainda não foi emitido. Para concluir o PIX de R$ {formatVal(rangeVal)}, realize o pagamento da taxa de emissão (R$ 27,00).
                </p>
                <button onClick={() => goTo(8)} className="w-full bg-destructive text-destructive-foreground font-black py-4 rounded-2xl uppercase text-sm shadow-lg">
                  Ativar Token e Receber PIX
                </button>
              </div>
            )}
          </div>
        </div>
      )}

      {/* Step 8: Queue */}
      {step === 8 && (
        <div className="animate-fade-in p-6">
          <div className="max-w-md mx-auto text-center mt-10">
            <div className="bg-primary text-primary-foreground p-6 rounded-4xl shadow-2xl mb-6">
              <h2 className="font-mont font-black text-xl uppercase italic mb-2">Token Ativado!</h2>
              <p className="text-[10px] opacity-80 font-bold tracking-widest uppercase">Processando Ordem de Pagamento</p>
            </div>

            <div className="bg-card p-8 rounded-4xl shadow-xl border border-border">
              <p className="text-muted-foreground text-[10px] font-bold uppercase mb-4 tracking-widest">Sua posição na fila de liberação:</p>
              <p className="text-7xl font-black text-foreground font-mont mb-4 italic">#{filaNum}</p>
              <p className="text-xs text-muted-foreground mb-8">Devido à alta demanda, seu PIX será enviado em até 4 horas.</p>

              <div className="bg-warning/10 border-2 border-warning/20 p-6 rounded-3xl mb-6">
                <p className="text-warning font-black text-xs uppercase mb-2">🚀 Quer pular para os 20 primeiros?</p>
                <p className="text-[10px] text-warning/80 font-bold mb-4 italic">
                  Ative o Fluxo Prioritário (R$ 34,00) e receba seu PIX em menos de 2 minutos.
                </p>
                <button className="w-full bg-warning text-warning-foreground font-black py-4 rounded-2xl uppercase text-[11px] shadow-md">
                  Pular Fila Agora
                </button>
              </div>
            </div>
          </div>
        </div>
      )}
    </div>
  );
};

export default Index;
