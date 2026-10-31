# W&M Sistema CFTV — Manual do Sistema

Sistema de gestão de clientes, orçamentos, serviços e finanças para empresas de segurança eletrônica.

Este README reúne todas as 15 seções do **Manual do Sistema** disponível em **Mais → Manual do Sistema**, acrescidas das funcionalidades atuais. Revisão documental: **31/10/2026**. Essa data não altera a versão exibida no aplicativo.

> Esta documentação mantém os tópicos do manual e descreve os cálculos atualmente implementados, sem alterar as regras do aplicativo.

## Sumário

- 1. Painel de Controle (Dashboard)
- 2. Cadastro de Clientes
- 3. Orçamentos — Criação e Envio
- 4. Fases do Orçamento
- 5. Serviços — Agendamento e Execução
- 6. Pagamentos e Recebimentos
- 7. Recibos e Envio via WhatsApp
- 8. Produtos e Serviços (Catálogo)
- 9. Reajuste de Preços
- 10. Balanço de Custos
- 11. Despesas
- 12. Relatórios
- 13. Exclusão de Registros
- 14. Gerenciamento de Prestadores
- 15. Configurações
- 16. Orçamento por voz com IA
- 17. Acesso e instalação
- 18. Sobre o sistema
- 19. Demonstração pública
- 20. Desenvolvimento e GitHub Pages

## 1. Painel de Controle (Dashboard)

A tela inicial exibe um resumo completo do seu negócio:

- Cards de resumo: total de orçamentos, serviços, receitas e despesas.
- Funil de Vendas: visualize a conversão desde orçamentos emitidos até pagamentos recebidos.
- Filtro por Prestador: selecione "Todos" para o funil geral ou escolha um prestador específico para ver apenas os dados dele.
- Visão do Dia: serviços agendados para hoje e os próximos 5 agendamentos, com dados do cliente, horário e status.

> Dica: O filtro por prestador atualiza automaticamente os cards de resumo e o funil de vendas.

## 2. Cadastro de Clientes

Gerencie todos os seus clientes com dados completos.

### Como cadastrar um novo cliente:

1. Acesse "Clientes" no menu inferior.
2. Toque no botão "+" para adicionar.
3. Preencha os dados: Nome, Telefone, E-mail, Endereço.
4. Adicione observações se necessário.
5. Toque em "Salvar" para finalizar.

### Dados disponíveis:

- Nome completo
- Telefone (obrigatório)
- E-mail (para envio de orçamentos)
- Endereço completo (rua, número, bairro, cidade, UF, CEP)
- Observações livres
- Status: Ativo ou Inativo

## 3. Orçamentos — Criação e Envio

Crie orçamentos profissionais com itens do catálogo, descontos e compartilhe com o cliente.

### Passo a passo para criar um orçamento:

1. Acesse "Orçamentos" no menu inferior.
2. Toque em "+" para criar um novo.
3. Selecione o cliente destinatário.
4. Adicione itens do catálogo (produtos/serviços), ajustando quantidade e valor.
5. Configure desconto (percentual) e prazo para início de execução. A validade inicial é de 15 dias.
6. Defina o percentual de mão de obra (padrão: 20%). Este valor será usado nos cálculos de custo do relatório.
7. Adicione observações se necessário.
8. Toque em "Criar Orçamento" para salvar como rascunho.

### Percentual de Mão de Obra:

Cada orçamento possui comissão/mão de obra configurável em **percentual** ou **valor fixo**. No modo percentual, o padrão é 20%, aplicado ao subtotal após desconto. A comissão é adicionada ao total e exibida no detalhe e nos relatórios.

### Compartilhamento:

- Baixar PDF: gera um documento PDF formatado para download.
- WhatsApp: abre o chat direto com o número do cliente cadastrado, com mensagem formatada e link de aceite.
- E-mail: envia o orçamento formatado em HTML para o e-mail do cliente, com botão de aceite e botões para responder por WhatsApp ou e-mail.

### Aceite pelo cliente:

Ao enviar um orçamento por **WhatsApp** ou **E-mail**, o cliente recebe um link/botão **"Aceitar Orçamento"**. Ao clicar:

1. O cliente é direcionado para uma página de confirmação.
2. O sistema atualiza automaticamente o status do orçamento para "Aprovado".
3. Você recebe a notificação de aprovação no painel do sistema.
4. Orçamentos vencidos ou já convertidos não podem ser aceitos pelo link.

> Dica: O link de aceite é único para cada orçamento e garante que o cliente aprove diretamente, sem necessidade de contato prévio.

## 4. Fases do Orçamento

Cada orçamento passa por fases que refletem o andamento do negócio:

- **Rascunho:** Orçamento criado mas ainda não enviado ao cliente. Pode ser editado livremente.

- **Enviado:** Orçamento enviado ao cliente (por WhatsApp ou e-mail). Aguardando resposta.

- **Aprovado:** O cliente aprovou o orçamento. Pronto para ser convertido em ordem de serviço.

- **Convertido:** Orçamento convertido em serviço. Uma ordem de serviço foi gerada automaticamente.

### Proteção de status:

Orçamentos com status **Convertido** ou **Recusado** ficam bloqueados. Gerar PDF, enviar por WhatsApp ou e-mail não altera o status — apenas permite visualização e reimpressão.

### Reabertura de orçamento vencido ou recusado:

Quando um orçamento está vencido (data de validade expirada) ou foi recusado, o sistema exibe um botão **"Reabrir Orçamento"**.

1. Abra o orçamento vencido ou recusado.
2. Toque no botão "Reabrir Orçamento".
3. O status será redefinido para "Rascunho".
4. A data de emissão será atualizada para hoje e a validade renovada por 30 dias.
5. O orçamento poderá ser editado e reenviado normalmente por todos os meios (PDF, WhatsApp, E-mail).

> Dica: Use a reabertura quando o cliente deseja retomar uma negociação após o vencimento do orçamento.

- **Recusado:** permanece no histórico e fica bloqueado até ser reaberto.
- **Vencido:** aparece em vermelho com a data de vencimento e integra o funil; ao reabrir deixa de ser vencido, e a conversão passa a ser acompanhada como serviço.

## 5. Serviços — Agendamento e Execução

Gerencie serviços do agendamento até a conclusão.

### Fases do serviço:

- 🗓️ Agendado: serviço marcado para uma data futura.
- 🔧 Em Execução: trabalho em andamento. Permite registrar pagamentos.
- ✅ Concluído: serviço finalizado. Permite registrar pagamentos e gerar recibos.
- ❌ Cancelado: serviço cancelado.

### Convertendo um orçamento em serviço:

1. Abra o orçamento aprovado.
2. Altere o status para "Convertido".
3. Um serviço será criado automaticamente vinculado ao orçamento.
4. Defina a data agendada e acompanhe na Visão do Dia.

### Ações disponíveis:

- Iniciar Execução: muda o status de "Agendado" para "Em Execução".
- Marcar como Concluído: finaliza o serviço e registra a data de conclusão.
- Registrar Pagamento: disponível para serviços em execução e concluídos.
- Gerar Recibo: disponível quando há pagamentos registrados.
- Excluir Serviço: serviços finalizados podem ser excluídos mediante senha de confirmação.

## 6. Pagamentos e Recebimentos

Registre pagamentos vinculados a serviços em execução ou concluídos.

### Como registrar um pagamento:

1. Acesse o serviço em execução ou concluído.
2. Na seção "Recebimentos", toque em "Registrar Pagamento".
3. Preencha: valor, forma de pagamento e número da NF (opcional).
4. Formas aceitas: Dinheiro, PIX, Cartão, Boleto.
5. Pagamentos via cartão podem incluir parcelamento (1x a 12x) com ou sem juros.
6. Pagamentos via PIX podem ter desconto à vista configurável (percentual).

### Barra de progresso:

O sistema exibe uma barra visual indicando quanto do valor total do serviço já foi pago, facilitando o acompanhamento dos recebimentos.

## 7. Recibos e Envio via WhatsApp

Gere recibos profissionais em PDF e compartilhe diretamente com o cliente.

### Gerando o recibo:

1. Acesse um serviço que tenha pagamentos registrados.
2. Role até o final da página.
3. Toque em "Gerar Recibo em PDF" para baixar o documento.
4. Ou toque em "Enviar Recibo via WhatsApp" para compartilhar.

### Envio via WhatsApp:

Ao enviar o recibo via WhatsApp, o sistema:

1. Gera o PDF do recibo automaticamente.
2. Abre a janela de compartilhamento com o PDF anexado (em dispositivos compatíveis).
3. Em seguida, abre o WhatsApp direto no chat do cliente com a mensagem formatada.

### Mensagem enviada:

A mensagem inclui saudação ao cliente, número da OS, valor total pago, agradecimento e dados de contato da empresa.

### Conteúdo do recibo PDF:

- Logo da empresa centralizado no topo.
- Número da OS e data de emissão.
- Dados do cliente (nome, telefone, e-mail).
- Informações do serviço (conclusão, prazo).
- Tabela detalhada de pagamentos (forma, data, valor).
- Resumo: valor do serviço, total pago e desconto aplicado.
- Observações do serviço (quando houver).
- Dados de contato da empresa no rodapé.

## 8. Produtos e Serviços (Catálogo)

O catálogo contém todos os itens que podem ser adicionados aos orçamentos.

### Informações de cada item:

- Código: identificador numérico único.
- Descrição: nome do produto ou serviço.
- Tipo: Produto ou Serviço.
- Unidade: unid, mt, cx, par, serv, etc.
- Valor Base: custo de aquisição (fornecedor).
- Valor Venda: preço de venda ao cliente.

Use a barra de busca para localizar itens rapidamente por código ou descrição.

## 9. Reajuste de Preços

Atualize os preços do catálogo em lote aplicando um percentual.

### Como reajustar:

1. Na tela "Produtos e Serviços", toque em "Reajustar".
2. Selecione os itens desejados (ou "Selecionar todos").
3. Informe o percentual: positivo para aumento, negativo para redução.
4. Escolha onde aplicar: Valor Base, Valor Venda ou Ambos.
5. Confirme a operação.

> Dica: Exemplo: +10% em Ambos irá aumentar tanto o custo quanto o preço de venda em 10%.

## 10. Balanço de Custos

Visualize a análise de custos de cada produto com margem de lucro.

### Informações exibidas por item:

- Custo WM: valor de compra/fornecedor.
- Custo Venda: valor cobrado do cliente.
- Mão de Obra: estimativa de 20% sobre o valor de venda do item do catálogo.
- Margem: diferença percentual entre custo WM e custo de venda.

### Resumo geral no topo:

- Custo WM Total
- Venda Total
- Mão de Obra Total (estimativa de 20% sobre a venda dos itens filtrados)
- Margem Total

## 11. Despesas

Registre despesas operacionais para controle financeiro.

### Tipos de despesa:

- ⛽ Combustível
- 🧰 Insumos
- 🔧 Manutenção
- 📦 Outros

### Campos:

- Descrição
- Valor
- Data
- Tipo
- Serviço vinculado (opcional)

## 12. Relatórios

Visão consolidada do desempenho financeiro com filtro por prestador.

### Filtro por Prestador:

Selecione um prestador específico para visualizar apenas os dados dele, ou escolha "Todos os prestadores" para o resumo geral. O filtro aplica-se a orçamentos, serviços, pagamentos e despesas.

### Resumo Geral:

- Orçamentos emitidos (quantidade)
- Total orçado (soma)
- Total aprovado
- Serviços realizados
- Total recebido
- Total despesas
- Lucro aproximado (receitas - despesas)
- Taxa de conversão

### Balanço de Custos (Serviços Concluídos):

- Receita total dos serviços concluídos
- Custo de mão de obra (baseado no % individual de cada orçamento)
- Custo de produtos (valor base dos itens)
- Lucro líquido (receita dos serviços concluídos menos custo WM dos produtos)

> Dica: O filtro por prestador permite avaliar a performance e o faturamento individual de cada profissional.

## 13. Exclusão de Registros

O sistema possui regras de exclusão para proteger a integridade dos dados.

### Exclusão por administradores:

Usuários com perfil de administrador podem excluir clientes, orçamentos, produtos, serviços, despesas e perfis de prestadores comuns. O gerenciamento de prestadores não inclui outros administradores ou o próprio usuário.

### Exclusão de orçamentos e serviços finalizados:

Orçamentos e serviços finalizados podem ser excluídos por qualquer usuário, mediante confirmação por senha de segurança.

### Exclusão em cascata:

Ao excluir um orçamento ou serviço, o sistema remove automaticamente todos os registros dependentes (pagamentos, despesas, itens) para garantir a integridade do banco de dados.

> Dica: A exclusão é irreversível. Certifique-se antes de confirmar a operação.

## 14. Gerenciamento de Prestadores

Administradores podem gerenciar os prestadores cadastrados no sistema.

### Exclusão de prestadores:

Na tela de **Configurações**, administradores visualizam a seção "Gerenciar Prestadores" com a lista de todos os prestadores (exceto o próprio admin). É possível excluir um prestador tocando no ícone de lixeira ao lado do nome.

> Dica: A exclusão de um prestador remove apenas o perfil. Registros associados (orçamentos, serviços) permanecem no sistema.

## 15. Configurações

Personalize o sistema de acordo com suas preferências.

- Tema: alterne entre modo claro e escuro.
- Perfil: edite nome, telefone e CPF/CNPJ.
- Conta: gerencie seus dados de acesso.
- Gerenciar Prestadores: disponível apenas para administradores (veja seção 14).

## 16. Orçamento por voz com IA

Na tela **Novo Orçamento**, o botão **Montar por voz (IA)** abre o ditado em português brasileiro. É necessário permitir o microfone em um navegador compatível; também é possível digitar o pedido.

1. Fale ou escreva o cliente, os produtos, quantidades e valores desejados.
2. Confira a transcrição e toque em **Gerar orçamento**.
3. A IA identifica itens do catálogo e o cliente, além de desconto, mão de obra, prazo e observações quando informados.
4. Revise o orçamento preenchido antes de salvar ou compartilhar.

A interpretação utiliza Lovable AI através de uma função do backend. Não exige chave privada no navegador. A disponibilidade e o consumo dependem do saldo e das condições de cobrança vigentes do workspace. A IA pode errar: o resultado não é enviado automaticamente ao cliente.

## 17. Acesso e instalação

- **Entrar:** acesso por e-mail e senha.
- **Cadastro:** criação de conta com confirmação de e-mail conforme configuração do ambiente.
- **Esqueci minha senha / Redefinir senha:** solicitação de link e definição de nova senha. A entrega depende da configuração de e-mails; não é garantia de envio.
- **Sair da conta:** encerra a sessão pelo menu Mais.
- **PWA:** permite instalação na tela inicial em navegadores compatíveis, com nome e ícones do sistema. Isso não significa que todos os recursos funcionem sem internet.
- **Página não encontrada:** trata endereços inexistentes.
- **Formatos:** português brasileiro, datas DD/MM/AAAA e moeda R$.

## 18. Sobre o sistema

A página **Sobre** reúne informações institucionais do desenvolvedor, logo, contato por WhatsApp, versão e data de atualização. Nenhuma informação de contato real é incluída na demonstração pública.

## Observações sobre a implementação atual

As seções anteriores cobrem os tópicos do manual. Na versão atual do código:

- **Total do orçamento:** subtotal menos desconto, mais comissão/mão de obra. Há escolha entre percentual e valor fixo; o percentual padrão é 20%.
- **Validade:** novos orçamentos recebem inicialmente 15 dias. Ao reabrir, a validade é renovada por 30 dias.
- **Prazo:** o campo se chama **Prazo para início de execução (dias)**; a conversão agenda o início a partir da aprovação e do prazo informado.
- **Balanço de Custos do catálogo:** a estimativa de mão de obra exibida nessa tela é 20% do preço de venda de cada item, não o percentual individual de cada orçamento. A margem é venda menos custo WM.
- **Relatórios:** lucro aproximado é recebimentos menos despesas. **Lucro líquido** usa somente serviços concluídos: receita desses serviços menos custo WM dos produtos. Mão de obra é exibida separadamente, não deduzida dessa fórmula.
- **Compartilhamento por e-mail:** utiliza conteúdo HTML e link digital de aceite, sem PDF anexado. O PDF pode ser baixado manualmente.
- **Catálogo:** permite cadastrar itens, pesquisar por código/descrição e reajustar preços. A quantidade corresponde aos registros existentes, não ao maior código.
- **Clientes:** o endereço pode ser auxiliado pela consulta de CEP, e há acesso à edição dos dados.
- **Permissões:** usuários comuns não visualizam administradores nos filtros. O gerenciamento de prestadores fica restrito a administradores e não permite administrar outros administradores ou o próprio usuário.

## 19. Demonstração pública

Abra **Mais → Exemplos com dados fictícios** ou `/demo.html#/painel` no ambiente de desenvolvimento. A demonstração tem navegação entre **25 páginas**, incluindo cadastro e edição de clientes, orçamentos, aceite, serviços, pagamentos, catálogo, balanço, despesas, relatórios, configurações, manual, sobre e telas de acesso.

### Isolamento

- Os dados são gerados exclusivamente em `src/demo/data.ts`.
- Não há conexão com banco, autenticação, funções de IA ou dados de clientes reais.
- Logos e contatos reais do cliente não são publicados: a identidade da demonstração é genérica.
- As alterações permanecem somente em memória e desaparecem ao recarregar. O botão de restaurar repõe os exemplos.
- É possível simular cadastro/edição, criar orçamento, converter em serviço, mudar o andamento, registrar pagamento, cadastrar produto, reajustar preços e lançar/excluir despesas.
- Voz/IA, acesso, recuperação de senha, aceite e mensagens são **simulações**, sem efeito externo. O pedido por voz aplica um exemplo predefinido, não interpreta qualquer texto.
- O download gera documento fictício TXT; a geração de PDFs reais continua disponível apenas no sistema principal.
- As telas são representações demonstrativas, não cópias funcionais conectadas das telas de produção. Alguns controles foram simplificados.
- No exemplo, datas e indicadores de referência são fixos para manter a apresentação reproduzível.

## 20. Desenvolvimento e GitHub Pages

### Executar o projeto

Requisitos: Node.js 22 e npm.

```sh
npm ci
npm run dev
npm run test -- src/demo/isolation.test.ts
```

Aplicativo principal: `http://localhost:8080/`. Demonstração: `http://localhost:8080/demo.html#/painel`.

### Publicar somente a demonstração

O fluxo `.github/workflows/demo-pages.yml` compila **somente** `demo.html` e suas dependências, com endereços relativos e navegação por hash. Não copia `public/`, não inclui o aplicativo conectado e não utiliza segredos de produção.

1. Conecte o projeto ao repositório no Lovable em **Configurações do projeto → Git**. A sincronização envia as alterações; o agente não executa comandos de commit/push.
2. No GitHub, abra **Settings → Pages → Build and deployment → Source → GitHub Actions**.
3. Confira se o repositório permite Actions e se o plano permite Pages com a visibilidade escolhida.
4. O fluxo executa em alterações relevantes nas branches `main` ou `master`. Se a branch sincronizada tiver outro nome, ajuste a lista de branches ou inicie o fluxo manualmente em **Actions → Publicar demonstração no GitHub Pages → Run workflow**.
5. Acesse o endereço informado pelo passo de publicação; normalmente `https://<usuario>.github.io/<repositorio>/`.

**Importante:** ativar esse fluxo publica a demonstração na página raiz desse repositório. Caso já exista outro site no Pages, utilize outro repositório ou adapte o destino antes de executar.

### Compilação independente

```sh
npm run build:demo
mv dist-demo/demo.html dist-demo/index.html
```

O resultado fica em `dist-demo/`. Não envie essa pasta gerada para o repositório; o fluxo a cria no GitHub. Não publique o `dist/` do aplicativo real como demonstração.

### Estrutura

- `src/pages/`: páginas do sistema real.
- `src/components/`: elementos de interface, documentos PDF e recursos específicos.
- `src/hooks/`: acesso e operações de dados.
- `src/demo/`: demonstração isolada e teste de segurança de dependências.
- `supabase/functions/`: funções do backend para aceite, e-mails e interpretação por IA.
- `vite.demo.config.ts`: compilação exclusiva do GitHub Pages.

### Replicação para outro cliente

Utilize **Remix** para instâncias independentes. Personalize logo e catálogo e confirme que cada instância utiliza seu próprio backend, usuários e armazenamento antes de inserir dados. Não reutilize a conexão do cliente original quando o requisito for isolamento entre empresas.

### Tecnologias e licença

React, TypeScript, Vite, Tailwind CSS, shadcn/ui, TanStack Query, Lovable Cloud, jsPDF, html2canvas e vite-plugin-pwa. Consulte `LICENSE` para os termos de licença do código.
