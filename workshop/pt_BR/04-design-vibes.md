<!-- l10n-sync: source-file="04-design-vibes.md" -->
# Parte 4: Tema Orientado a Design

---

Nesta parte, você vai usar o **Plan Mode** para projetar uma transformação visual completa e o **Agent Mode** para implementá-la. Isso é desenvolvimento orientado a design — comece com a visão, itere nos visuais e deixe o Copilot cuidar do trabalho pesado de CSS.

## Tarefa 1: Planeje o Tema Retrô

<!-- track:vscode:start -->
Mude para o modo **Plan** no GitHub Copilot Chat.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Use `/plan` no GitHub Copilot CLI ou pressione **Shift+Tab** até ativar o plan mode.
<!-- track:cli:end -->

Insira este prompt:

> Quero transformar esta página em uma experiência completa de fliperama retrô. Planeje uma reformulação visual abrangente que inclua: efeitos de linhas de varredura CRT no fundo, brilho neon pulsante no título como um letreiro luminoso, selo VS animado com mudanças de gradiente, sobreposição de brilho nos cartões de resultados, animações de entrada flutuante nos campos, texto de carregamento que muda entre verde e roxo e efeitos de brilho ao passar o cursor sobre os quadrados de contribuição. Mantenha o fundo escuro (`#0a0a1a`) e as cores de destaque verde (`#5fed83`) e roxo (`#8a2be2`). Use um tema escuro com a fonte retrô Press Start 2P do Google Fonts.

O Copilot vai gerar um plano de implementação detalhado cobrindo todos os efeitos visuais. **Não aceite imediatamente** — revise o plano e itere:

- Sugira ajustes no tempo das animações (ex.: "Deixe a pulsação do neon mais lenta, em torno de 3 segundos").
- Pergunte sobre efeitos específicos (ex.: "Como a sobreposição de brilho vai funcionar nos cartões?").
- Solicite mudanças na abordagem se algo não parecer correto

Quando estiver satisfeito com o plano, peça ao Copilot para implementá-lo.

## Tarefa 2: Implemente o Tema

Peça ao Copilot para implementar o plano que vocês acabaram de criar:

> Implemente o plano de tema de fliperama retrô que acabamos de criar.

O Copilot vai adicionar múltiplas animações CSS, pseudo-elementos e transições na sua folha de estilos. Isso pode incluir:

- `@keyframes` para scanlines, pulso neon, shimmer e efeitos de float-in
- Pseudo-elementos (`::before`, `::after`) para efeitos de sobreposição
- CSS custom properties para as cores do tema
- Estados de transição e hover para elementos interativos

<!-- track:cli:start -->
Depois que as alterações forem aplicadas, use `/diff` para revisar a estilização antes de aprová-la.
<!-- track:cli:end -->

<!-- track:vscode:start -->
Depois que as alterações forem aplicadas, **verifique a pré-visualização no seu navegador** para ver a transformação completa do tema retrô arcade.
<!-- track:vscode:end -->

## Tarefa 3: Ajuste Fino das Vibes

> **⚠️ Não está vendo as alterações?** Se o novo tema ou as animações não aparecerem, pare o servidor de desenvolvimento (`Ctrl+C`), reinicie com `npm run dev` e atualize a página forçadamente (`Ctrl+Shift+R`) no navegador.

Mantenha a pré-visualização do navegador aberta e itere no design. Tente prompts como:

> O efeito das linhas de varredura está forte demais; reduza a opacidade para 0.03.

> Adicione uma cintilação elétrica sutil ao texto do título.

> O selo VS deveria pulsar com mais intensidade.

Isso é **desenvolvimento orientado a design** — você está iterando na saída visual em tempo real. Cada prompt refina a experiência até que fique perfeita. Não se contente com "bom o suficiente" — aperfeiçoe as vibes até que a página pareça pertencer a um gabinete de arcade.

## Tarefa 4: Atualize as Instruções

<!-- track:vscode:start -->
As instruções do workspace devem refletir as principais decisões de design. Peça ao Copilot:

> Adicione uma seção de guia de design a copilot-instructions.md descrevendo o tema de fliperama retrô: cores, fontes e estilo das animações.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Peça ao Copilot CLI:

> Atualize as instruções do repositório com um guia de design curto para o tema de fliperama retrô: cores, fontes, estilo das animações e a regra de manter a estética neon em novas interfaces.
<!-- track:cli:end -->

Isso mantém as futuras interações com o Copilot alinhadas à identidade visual definida. Qualquer funcionalidade ou componente novo seguirá a estética retrô arcade.

Faça commit das instruções e das alterações de design quando a página estiver como você quer.

## ✅ Parte 4 Concluída

**O que você aprendeu:**

- **Plan Mode para sistemas de design** — esboce uma reformulação visual completa antes de escrever qualquer código
- **Iterar na saída visual** — use prompts rápidos de acompanhamento para ajustar animações, cores e efeitos
- **Manter as instruções atualizadas com decisões de design** — documente seu tema para que o Copilot mantenha a consistência
- **Fluxo de desenvolvimento orientado a design** — comece com a visão, implemente com IA, refine até ficar perfeito
