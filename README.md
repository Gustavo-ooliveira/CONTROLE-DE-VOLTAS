# Controle de Voltas

Sistema web para controlar o fluxo de bilhetes de volta cancelados e reemitidos (solicitação, emissão e entrega), desenvolvido para a rotina de uma empresa de venda de passagens aéreas por milhas. Está em uso diário por 3 pessoas.

## O problema

Os pedidos de volta eram controlados em planilha. Não havia um lugar para guardar os passaportes nem um aviso dos pedidos que precisavam ser solicitados no dia. Quando alguém esquecia, o prazo de entrega passava.

## O que o sistema faz

- Cadastro de pedidos com agência, cliente, trecho, data e hora de entrega e prazo (24h/48h)
- Abas por etapa: voltas de hoje, aguardando entrega, todas as voltas e finalizadas
- Status por pedido: solicitado, emissor (Lucas/Speed) e entregue
- Alerta sonoro e visual 5 minutos antes da hora de entrega
- Destaque por urgência (atrasado, entrega próxima, concluído) e cartões de resumo
- Aviso de pedido duplicado (mesmo cliente e mesma data de entrega)
- Cadastro de passageiros com validação de CPF
- Upload de passaportes e do documento final por pedido
- Geração do texto de solicitação para WhatsApp
- Filtros por agência, emissor e busca por cliente, trecho ou data
- Tema claro e escuro
- Perfil somente leitura, com permissões aplicadas no banco

## Tecnologias

- **Banco de dados:** PostgreSQL (Supabase)
- **Autenticação e armazenamento de arquivos:** Supabase Auth e Storage
- **Segurança:** Row Level Security (RLS) com políticas por perfil
- **Front-end:** HTML, CSS e JavaScript
- **Hospedagem:** Netlify

## Modelagem

Duas tabelas principais: `Controle de voltas` (pedidos) e `passageiros`, ligada ao pedido por chave estrangeira. Uma tabela de perfis define o papel de cada usuário (leitura ou edição).

## Como rodar

1. Crie um projeto no Supabase e as tabelas do sistema.
2. Copie `config.exemplo.js` para `config.js` e preencha a URL e a chave do seu projeto.
3. Abra o `index.html` no navegador.

## Observação

Os dados reais (clientes, CPFs, passaportes) não fazem parte do repositório. O `config.js` com as credenciais também não é versionado.

## Autor

Gustavo, em transição de carreira para a área de dados.
