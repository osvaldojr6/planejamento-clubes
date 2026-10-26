# Planejamento de Clubes — Elenco Studio

Aplicação de planejamento de elencos de futebol em português, feita com HTML, CSS e JavaScript, sem etapa de build.

## Funcionalidades

- Organização de atletas por posição e busca por nome.
- Valores de mercado estimados e editáveis por jogador.
- Total estimado do elenco projetado, atualizado conforme as decisões.
- Decisões: a definir, fica no elenco, vender, **não renovar**, **rescindir contrato** e contratar.
- Cadastro e edição de nome, posição, idade, camisa, fim do contrato e valor estimado.
- Escalações 4-3-3, 4-2-3-1, 4-4-2 e 3-5-2, com escolha manual ou preenchimento automático por posição.
- Exclusão dos atletas com saída planejada das opções de escalação.
- Resumo das movimentações, salvamento no navegador, backup em JSON e importação validada.
- Exportação da escalação em SVG e compartilhamento de uma cópia do planejamento por link quando hospedado.
- Layout adaptável para computador e celular.

## Executar

Abra `index.html` no navegador. Para servir localmente, se tiver Python instalado:

```sh
python -m http.server 8080
```

Acesse `http://localhost:8080`.

O projeto também pode ser hospedado como site estático. Use a raiz deste repositório como pasta de publicação; não há instalação de dependências nem comando de build.

## Arquivos

| Arquivo | Responsabilidade |
| --- | --- |
| `index.html` | Estrutura e telas |
| `style.css` | Identidade visual e adaptação às telas |
| `app.js` | Dados de demonstração, decisões, escalação e persistência |

## Dados e limites

O elenco inicial e os valores são **fictícios, para demonstração**. A aplicação não consulta uma base de jogadores nem calcula avaliações de mercado automaticamente. As estimativas devem ser editadas pelo usuário.

O total projetado inclui atletas sem decisão, permanências e contratações. Vendas, não renovações e rescisões são consideradas saídas do plano. O valor de mercado não representa receita de venda, preço de contratação ou multa rescisória.

As moedas EUR, BRL e USD identificam a unidade das estimativas. Alterar a moeda não converte os valores por câmbio.

Os dados ficam no armazenamento local do navegador, sem conta, servidor de dados ou sincronização entre dispositivos. Exporte um backup antes de limpar os dados do navegador. Um link compartilhado carrega uma cópia do planejamento no próprio endereço; a pessoa que recebe ainda precisa ter acesso ao site. Na versão aberta como arquivo local, use o backup JSON para compartilhar.

As fontes são carregadas do Google Fonts quando há conexão; fontes alternativas mantêm o funcionamento sem essa conexão.

## Verificação realizada

- Validação de sintaxe JavaScript.
- Teste no navegador de não renovação e rescisão, contagem de saídas e recálculo do valor projetado.
- Conferência da persistência após recarregar a página.
- Edição de valor, mudança de permanência e filtro por nome.
- Preenchimento de escalação respeitando atletas indisponíveis.

Ainda não há uma suíte automatizada de testes.
