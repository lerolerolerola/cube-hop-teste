# Cube Hop — Documentação

Documento para quem vai usar, testar, apresentar ou continuar o jogo (equipa, entrevistas, terceiros).
Jogar: https://lerolerolerola.github.io/cube-hop/ · Código: https://github.com/lerolerolerola/cube-hop

---

## 1. O que é

Cube Hop é um jogo de plataformas em pixel art para telemóvel, feito para estudar **design para o desengajamento**: como ajudar uma criança a **parar de jogar de forma saudável**, sem castigos nem manipulação.

Joga-se como um jogo normal (D-pad e botões A/B). Os **sensores do telemóvel não são controlos**: servem só para as pausas e para terminar a sessão.

Há duas versões com a mesma interface. **Escolhe-se no ecrã inicial**, com os botões **COM O PIP** / **SEM MASCOTE** (a escolha fica guardada):

| Versão | Para quê |
|---|---|
| **Sem mascote** | O jogo com todas as ferramentas de pausa e fim de sessão |
| **Com mascote (Pip)** | Igual, mais uma mascote que guia a criança e fica contente com as pausas feitas em conjunto. As atividades passam a ser feitas *com* o Pip |

Também se pode abrir já com o Pip escolhido com `.../cube-hop/?mascot`, ou mudar em Adultos → *Mascote (versão de teste)*.

### Endereços úteis

| Endereço | Para quê |
|---|---|
| `.../cube-hop/` | O jogo normal |
| `?mascot` | Abre com o Pip escolhido |
| `?dev` | Modo de teste (secção 8) |
| `?lang=pt` / `?lang=en` | Força uma língua (secção 10) |

Podem juntar-se: `?mascot&dev&lang=pt`.

### Requisitos

- Um browser recente no telemóvel (Chrome no Android, Safari no iPhone), com o telemóvel **deitado** (na vertical aparece "Vira o telemóvel de lado").
- **HTTPS** para os sensores funcionarem. O GitHub Pages já serve em HTTPS.
- No iPhone, o jogo pede permissão de "Movimento e Orientação" ao carregar em CONTINUAR / NOVO JOGO. Sem ela, as atividades de movimento e a de pousar o telemóvel não funcionam.
- Também se joga no computador, com o teclado (útil para testes).

---

## 2. Como jogar

| Telemóvel | Computador | Ação |
|---|---|---|
| D-pad ◀ ▶ | Setas / A D | Andar |
| A (ou ▲ no D-pad) | Espaço / W / ↑ | Saltar; carregar outra vez no ar = salto duplo |
| B | Shift / X | Dash (um por salto, elimina inimigos) |
| Abanar com força | Manter **E** | Simula um "abanão de raiva" |
| Pousar virado para baixo | Manter **F** | Simula o telemóvel virado para baixo |

**6 níveis**, cada um ensina ou junta movimentos: 1 salto · 2 salto duplo (paredes altas) · 3 dash (buracos largos) · 4 tudo junto, com inimigos mais rápidos · 5 grutas com mais espinhos · 6 o mais difícil, com os inimigos mais rápidos. Cada nível mostra uma dica quando começa.

**Versão vertical e horizontal:** no ecrã inicial escolhe-se **VERTICAL** ou **HORIZONTAL** (a escolha fica guardada; da primeira vez segue a posição do telemóvel). A horizontal tem os 6 níveis acima. A vertical tem **3 níveis a subir** até uma porta lá em cima (1 Torre · 2 Desfiladeiro, que pede salto duplo · 3 Céu, que pede dash); com o telemóvel em pé o nível fica entre a barra de cima e os comandos, deitado fica numa coluna ao centro. Cada versão tem o seu progresso guardado. No computador, `?tall` força a vertical.

**Instalar como aplicação:** no iPhone, Safari → Partilhar → *Adicionar ao ecrã principal*; no Android, Chrome → menu → *Instalar aplicação*. Abre em ecrã inteiro, sem as barras do browser, e depois de aberto uma vez funciona sem internet.

- **Cubos:** apanham-se pelos níveis e ficam guardados. Ao apanhar o primeiro aparece uma explicação; tocar no contador de cubos mostra-a outra vez.
- **Checkpoint (bandeira):** ativa ao passar pela coluna da bandeira, mesmo a saltar por cima. Ao morrer, volta-se ao último checkpoint.
- **Depois de morrer:** durante 2 segundos os inimigos não fazem mal (o boneco pisca), para um inimigo parado em cima do checkpoint não matar a criança sem parar. Espinhos e quedas continuam a matar.
- **Progresso:** fica guardado no início de cada nível.

### O ecrã de jogo

Na barra de cima, da esquerda para a direita:

| Elemento | O que mostra |
|---|---|
| Cubo e número | Cubos apanhados |
| Nome do nível | Ex. "1 · ALDEIA" (escondido em ecrãs estreitos) |
| Pip e corações | Só na versão com mascote: a energia do Pip (secção 7) |
| NV e barra | Nível de autonomia e quanto falta para o próximo (secção 3) |
| Relógio | Tempo que falta de jogo. Depois de "Acabar este nível", mostra os 2 minutos que faltam |
| Botão de ferramentas | Só no modo de teste (secção 8) |
| Botão de respirar | Só aparece quando os controlos estão trocados por um abanão (secção 6) |
| Som e pausa | Ligar/desligar o som; pausa, com "Continuar" ou "Parar de jogar" |

---

## 3. Como corre uma sessão

```
Início ──► jogar ──► pausa a cada N min ──┬─► faz uma atividade ──► volta a jogar (contador a zero)
                                          ├─► "Agora não" ──► a pausa volta 1 min depois
                                          └─► "Parar de jogar por hoje" ──► cartão final
Muito tempo seguido sem fazer pausa ──► fricção crescente, até fazer uma pausa
Perto do fim ──► aviso (cores cinzentas, música abranda) ──► "Acabou o tempo!"
             ──► acabar o nível (máx. 2 min) ou parar ──► cartão final
```

O tempo de jogo do dia fica guardado: parar e carregar em CONTINUAR não reinicia o relógio.

**Autonomia:** pontos que a criança ganha quando para por si. Só sobem, ficam guardados entre dias e estão divididos em níveis (o nível 1 precisa de 10 pontos, cada nível seguinte mais 5), para haver sensação de progresso. O nível aparece no ecrã inicial e na barra de cima.

| Ação | Pontos |
|---|---|
| Fazer a pausa logo que é pedida | +3 |
| Fazer a pausa depois de "Agora não" | +2 |
| Parar antes de o tempo acabar | +5 |
| Parar quando o tempo acaba (ou acabar o nível nos 2 min) | +4 |
| Acalmar depois do abanão | +1 |
| Ser parada à força (não acabou o nível nos 2 min) | 0 |

Os adultos veem o nível e os pontos no painel e podem repor a autonomia.

### Princípios e onde aparecem

Princípios que extraímos do artigo *Designing for Disengagement* (Alsheail, Alexandrovsky e Gerling, 2023).

| Princípio | No jogo |
|---|---|
| **Autonomia** | Botão de pausa com "Parar de jogar" a qualquer momento; a criança escolhe a atividade da pausa ou adia-a ("Agora não"); "Parar de jogar por hoje" em todas as pausas; "Parar aqui" depois de cada nível; a fricção desaparece assim que faz uma pausa |
| **Transição gradual** | Aviso antes do fim; as cores desvanecem para cinzento e a música abranda |
| **Conclusão satisfatória** | Quando o tempo acaba, a criança tem 2 minutos para acabar o nível atual e recebe um cartão final |
| **Continuidade** | O progresso fica guardado (retoma no início do nível), e o tempo de jogo do dia também |
| **Contexto social** | Painel de adultos (atrás de uma conta de multiplicar); o cartão final diz "Conta a um adulto o que fizeste hoje" |
| **Evitar manipulação** | Sem prémios por ficar, sem streaks, sem temporizadores que puxam a criança de volta; não há tempo extra |

---

## 4. Pausas com atividades (os sensores como ferramentas)

A cada N minutos (definido pelo adulto) o jogo para e mostra a lista de atividades. A criança **escolhe** uma. Por baixo, separadas, estão as opções **"Agora não"** (a pausa volta passado 1 minuto) e **"Parar de jogar por hoje"**. Fazer uma atividade põe a zero o contador de tempo seguido sem pausa (secção 5).

| Atividade | O que a criança faz | Sensor | Como o jogo verifica |
|---|---|---|---|
| **Encontrar uma cor** | Aponta a câmara a algo da cor pedida, enche o quadrado e carrega em TIRAR FOTO | Câmara | Pelo menos 30% do quadrado central tem essa cor |
| **Dar uma volta** | Anda N passos (por defeito 20) com o telemóvel na mão | Acelerómetro | Conta os picos de aceleração |
| **Respirar** | Segura o telemóvel quieto e respira com o círculo (8 s) | Acelerómetro | Movimento muito baixo; mexer faz a barra recuar |
| **Cantarolar** | Cantarola uma música durante 3 s | Microfone | Volume acima de um limiar |
| **Sesta do telemóvel** | Pousa o telemóvel **com o ecrã para baixo** durante X segundos (por defeito 60) e vai fazer outra coisa | Orientação | O telemóvel está virado ao contrário (inclinação > 150°). **Se o levantar, o tempo recomeça do zero** |

**Porque é que a sesta do telemóvel é diferente:** nas outras atividades a criança continua a usar o telemóvel. Nesta, a pausa é **não usar o telemóvel de todo**. Há um som quando é bem pousado, um som grave se for levantado e um som de vitória no fim, por isso a criança não precisa de olhar para o ecrã.

Em cada atividade, **"Voltar"** regressa à lista sem penalização.

---

## 5. Fricção e fim do tempo

A fricção está ligada a comportamentos (fugir das pausas, frustração) e não ao relógio. O fim do tempo não tem castigos.

### Os dois sinais visuais

Para não se confundirem, os dois casos têm sinais diferentes:

| Situação | Sinal |
|---|---|
| O tempo está a acabar | As cores vão ficando **cinzentas** e a música abranda |
| Muito tempo seguido sem pausa | A imagem fica com **tom sépia**; a música só muda depois (desafina) |

### Jogar muito tempo seguido sem pausa

O jogo conta o tempo de jogo desde a **última pausa feita**. Adiar pausas ("Agora não") faz esse tempo crescer. Quando passa do limite definido pelo adulto (por defeito 10 minutos), o jogo vai ficando estranho, aos poucos:

| Tempo seguido sem pausa | Efeito |
|---|---|
| 10 min | Aviso "Estás a jogar há muito tempo sem pausa! Faz uma pausa para o jogo voltar ao normal"; imagem com tom sépia |
| 12 min | Cores em negativo e música desafinada |
| 14 min | Esquerda e direita trocadas |
| 16 min | O jogo ignora alguns saltos |

**Fazer qualquer atividade de pausa repõe tudo** e põe o contador a zero. A saída está sempre nas mãos da criança: quem faz as pausas nunca vê estes efeitos, por mais que jogue na semana.

O adulto pode mudar o limite (0 = desligado) e desligar o negativo, a troca de controlos e os saltos ignorados. Se as pausas estiverem desligadas, esta fricção também fica desligada (não haveria forma de a desfazer).

### Frustração

Abanar o telemóvel com raiva troca a esquerda e a direita durante 30 segundos. Aparece um botão de respirar na barra de cima; acalmar (segurar o telemóvel quieto) repõe os controlos.

### Fim do tempo (sessão ou semana)

Não há tempo extra nem castigos. Quando acaba o tempo da sessão ou o tempo da semana:

1. **2 minutos antes:** aviso "Está quase na hora de parar! Tenta acabar este nível"; as cores desvanecem para cinzento e a música abranda.
2. **"Acabou o tempo!"**, com três opções: **Acabar este nível** (tem 2 minutos, que aparecem no relógio), **Parar agora**, ou **+5 min** (só com o adulto).
3. Se acabar o nível dentro dos 2 minutos, recebe "Acabaste mesmo a tempo!" e o cartão final. Se os 2 minutos passarem, o jogo termina sozinho com o cartão final. O progresso fica guardado no início do nível.

### Tempo diário e semanal

O tempo de cada sessão conta por dia e o total conta por semana (na versão final, assumimos que é medido pelo plug-in). Quando acaba o tempo do dia, o jogo fica bloqueado até ao dia seguinte; quando acaba o da semana, até segunda-feira. Um adulto pode repor o tempo.

---

## 6. Ecrãs finais

- **Nível completo:** mostra os cubos e que o progresso está guardado, com "Próximo nível" ou "Parar aqui".
- **Cartão final:** minutos jogados hoje, cubos, pontos de autonomia ganhos e "Conta a um adulto o que fizeste hoje".

---

## 7. Versão com mascote (Pip) — em teste

**Pergunta de investigação:** *faz sentido ter uma mascote que guia a criança a usar estas ferramentas?*

O Pip é um ursinho amarelo que aparece no topo do ecrã (com 5 corações de **energia**) e nos cartões, a falar com a criança.

| Situação | O que o Pip diz ou faz | Energia |
|---|---|---|
| Chega a hora da pausa | Pede uma das atividades ligadas, ex. "O Pip quer ir passear! Vamos levá-lo a dar uma volta?" (a lista continua a mostrar todas) | −1 (só a primeira vez, não quando volta depois de adiada) |
| Atividade **bem feita** | Uma frase sobre o que fizeram juntos, ex. "Que passeio tão bom! O Pip esticou as patas." / "O Pip adorou a tua música!" (fica contente) | +2 |
| Desiste da atividade ("Voltar") | "Não faz mal! O Pip ainda está um bocadinho cansado." (sem ralhar) | 0 |
| Adia a pausa ("Agora não") | Quando a pausa volta: "O Pip ainda está à espera da pausa…" | 0 |
| Acalma-se depois de um abanão | "O Pip também está calmo" | +1 |
| Abana o telemóvel com raiva | O Pip fica assustado enquanto os controlos estão trocados | — |
| Joga muito tempo sem pausa | O Pip fica mais cansado a cada passo da fricção (10, 12, 14, 16 min) | −1 por passo |
| Para a tempo (qualquer botão de parar, ou acaba o nível nos 2 min) | "Obrigado por parares a tempo! O Pip vai dormir" | +1 |
| Acabou o tempo | "O Pip está a ficar com sono. Vamos acabar este nível e descansar!" | — |
| Os 2 minutos para acabar o nível passam | "O Pip vai dormir. Para a próxima, paramos um bocadinho mais cedo!" | 0 |

**Atividades com o Pip:** os nomes mudam para envolver a mascote: *Mostrar uma cor ao Pip* · *Levar o Pip a passear* · *Respirar com o Pip* · *Cantar para o Pip* · *Pôr o Pip a dormir* (pousar o telemóvel = pôr o Pip a dormir).

**Humor do Pip:** 4–5 corações contente · 2–3 normal · 0–1 triste (mais pálido) · assustado durante o abanão · a dormir no cartão final.

**Decisões de design (para discutir nas entrevistas):**
- **O Pip nunca perde energia enquanto o jogo está fechado.** Ao contrário de um Tamagotchi, não há nada que puxe a criança de volta ao jogo.
- O Pip **dorme no fim da sessão**: parar de jogar é apresentado como algo bom para a mascote, não como uma perda.
- Falhar, desistir ou adiar uma atividade **não tira energia**, só não dá. Só jogar muito tempo seguido sem pausa a tira.
- A energia fica guardada entre sessões e não há prémio por ter os corações cheios.

**Perguntas sugeridas para as entrevistas:**
1. A criança percebeu que as atividades deixam o Pip contente? Fez as pausas mais vezes por causa disso?
2. Ficou triste ou ansiosa quando o Pip ficou cansado? (risco de culpa)
3. Ver o Pip a dormir ajudou a aceitar o fim do jogo?
4. Os pais preferem a versão com ou sem mascote? Porquê?
5. O Pip devia ter nome/aspeto escolhido pela criança?

---

## 8. Modo de teste (dev)

Abrir com `?dev` (ou Adultos → Testes → Modo dev). Aparece um botão de ferramentas na barra de cima:

- **Saltar o relógio:** Pausa, Abrandar, O tempo acabou, e 10/12/14/16 min sem pausa (cada passo da fricção). A sequência real acontece, seguindo as definições dos adultos. "Repor relógio" volta ao início.
- **Um efeito de cada vez:** Cinzento, Negativo, Música lenta/desafinada, Trocar controlos, Ignorar saltos, Abanar zangado, Gastar tempo semanal.
- No computador, cada atividade tem um botão **"Saltar (teste PC)"**; a sesta do telemóvel pode ser testada mantendo a tecla **F**.
- Quando o tempo acaba, o ecrã inicial mostra "REPOR TEMPO (TESTE)".

O modo de teste não gasta o tempo semanal.

**Para uma demonstração rápida numa entrevista:** abrir `?dev` → COM O PIP → NOVO JOGO → botão de ferramentas → Pausa → Pôr o Pip a dormir → pousar o telemóvel.

---

## 9. Painel dos adultos

**Guia para adultos:** na primeira vez que o jogo é aberto aparece um guia de 6 passos (tempo de jogo, pausas, fim do tempo, privacidade e este painel), que termina com *Configurar agora* ou *Mais tarde*. Com `?tutorial` no endereço, o guia aparece outra vez.

Botão **Adultos** no ecrã inicial, protegido por uma conta de multiplicar. Tudo é guardado só no próprio telemóvel. O **X** no canto, sempre visível, fecha sem guardar.

| Grupo | Definições (valores por defeito) |
|---|---|
| Tempo | Sessão de jogo (15 min) · Pausa com atividade a cada (5 min, 0 = nunca) · Começar a abrandar (2 min antes do fim) · Tempo de jogo por semana (120 min) |
| Atividades de pausa | Encontrar uma cor · Andar (passos a dar: 20) · Respirar · Cantarolar · Pousar o telemóvel virado para baixo (segundos: 60) |
| Cores a encontrar | Vermelho, laranja, amarelo, verde, azul, roxo |
| Abrandar | As cores vão ficando cinzentas · A música abranda perto do fim e desafina se jogar muito tempo sem pausa |
| Jogar muito tempo sem pausa | A fricção começa após (10 min sem pausa, 0 = nunca) · Negativo (+2 min) · Trocar controlos (+4 min) · Ignorar saltos (+6 min) |
| Frustração | Abanar com raiva troca os controlos |
| Mascote | Pip (versão de teste) |
| Testes | Modo dev |

"Passos a dar", "Segundos virado para baixo" e "Cores a encontrar" só aparecem quando a atividade correspondente está ligada.

No fundo do painel: **Guardar**, **Repor o nível de autonomia**, **Repor o tempo desta semana** e **Cancelar**.

---

## 10. Línguas (CSV)

Todo o texto do jogo (botões, cartões, mensagens, nomes e dicas dos níveis, definições, falas do Pip) está separado do código, em `languages.csv`: uma linha por texto, uma coluna por língua (`key,en,pt`). O jogo usa a língua do telemóvel se existir no ficheiro, senão inglês. Para testar outra língua: `?lang=pt`.

Isto é para quem desenvolve o jogo (não há opção no painel dos adultos):
- Editar `languages.csv` no Excel / Google Sheets e gravar como **CSV UTF-8** (`;` também funciona). Para uma língua nova, acrescentar uma coluna (ex. `fr`). Células vazias usam o inglês.
- Não mexer na coluna `key`. `{nome}` é preenchido pelo jogo (ex. `{min}`), `:nome:` é um ícone (ex. `:play:`), uma quebra de linha na célula é uma quebra de linha no jogo.
- `node lang.test.js` confirma que não falta nenhum texto. Depois, subir o `?v=` em `index.html`.

---

## 11. Privacidade

- Nada é enviado para lado nenhum. Não há contas, servidores nem analítica.
- Câmara e microfone só são usados **durante** a atividade correspondente e desligam-se logo a seguir. As imagens são analisadas no telemóvel e não são guardadas.
- Progresso, definições, tempo, autonomia e energia do Pip ficam no `localStorage` do browser, só nesse telemóvel. Limpar os dados do site apaga tudo.

---

## 12. Para quem quer mexer no código

HTML, CSS e JavaScript sem dependências nem build. O jogo **não abre com duplo clique** no `index.html` (o browser bloqueia a leitura do `languages.csv`); é preciso um servidor local, por exemplo:

```bash
python3 -m http.server 8000
```

e ir a `http://localhost:8000/?dev`. Para testar sensores no telemóvel é preciso HTTPS (o GitHub Pages serve).

| Ficheiro | Conteúdo |
|---|---|
| `index.html` | Estrutura: canvas, barra de cima, comandos, ecrã inicial |
| `style.css` | Aspeto de tudo o que não é o canvas (cartões, botões, barra de cima) |
| `languages.csv` | Todo o texto do jogo, uma coluna por língua (secção 10) |
| `lang.js` | Lê o CSV; `tr('chave')` devolve o texto na língua do jogo |
| `lang.test.js` | Verificação: `node lang.test.js` confirma que todos os textos usados existem no CSV |
| `icons.js` | Ícones em pixel art; escreve-se `:nome:` no texto (ex. `:play:`) |
| `levels.js` | Os 6 níveis em texto (`#` chão, `B` tijolo, `o` cubo, `^` espinhos, `E` inimigo, `F` checkpoint, `D` porta, `P` início) e as cores de cada um; `CLIMB_LEVELS` são os 3 níveis a subir (12 blocos de largura) |
| `game.js` | Motor do jogo: física, desenho, som, comandos |
| `session.js` | Tudo o que é sessão: tempo, pausas, atividades, fricção, painel dos adultos, modo de teste |
| `mascot.js` | Versão com mascote. Envolve funções do `session.js` sem as alterar; com a mascote desligada o jogo é igual à versão base |
| `gdevelop/` | Exportação dos níveis para um projeto GDevelop (só design de níveis); `python3 gdevelop/make.py` gera-o a partir do `levels.js` |

**Adicionar um nível:** juntar um bloco ao fim de `LEVELS` em `levels.js` (11 linhas de mapa, com um `P` e uma `D`), acrescentar `levelN.name` e `levelN.hint` ao `languages.csv`, e o número do nível na lista do `lang.test.js`.

**Adicionar uma atividade de pausa:** criar uma função `nome(done, back)` em `session.js` (ver `rest` ou `calm` como exemplo), juntá-la a `ACTS`, acrescentar a opção em `DEFAULTS` e `FORM`, e os textos novos em `languages.csv` (incluindo `pip.act.nome`, `pip.nome`, `pip.done.nome` e `pip.ask.nome` para a versão com mascote).

**Publicar:** o GitHub Pages publica o ramo `main`. Depois de alterar ficheiros, subir o número `?v=` em `index.html` para os telemóveis carregarem a versão nova.

**Se um ficheiro não carregar** (por exemplo, com rede fraca), a página recarrega sozinha uma vez.

---

## 13. Créditos

- Ícones: [Pixelarticons](https://github.com/halfmage/pixelarticons), de Gerrit Halfmann (licença MIT).
- Fontes: Press Start 2P, Pixelify Sans e VT323, do Google Fonts (licença SIL Open Font License).
