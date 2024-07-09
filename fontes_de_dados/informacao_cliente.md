# Fontes de Dados

Neste workshop, utilizamos diversas fontes de dados para criar uma visão de 360 graus do cliente. Abaixo estão as descrições das principais fontes de dados e os detalhes de suas respectivas estruturas.

## Informações do Cliente

**Fonte:** CRM  
**Formato de Origem:** API - JSON  
**Colunas:**
- ID do Cliente
- Idade
- Data de nascimento
- Status de proprietário da casa
- Ocupação
- Estado civil
- Chefe da família
- Data de criação do cliente

## Transações

**Fonte:** Fontes de mainframe  
**Formato de Origem:** Banco de dados relacional  
**Colunas:**
- ID da transação (trans_id)
- ID da conta (ID_da_conta)
- Data
- Tipo
- Operação
- Quantia
- Saldo

## Cartão de Crédito

**Fonte:** Sistema de originação de cartões  
**Formato de Origem:** Arquivo de texto - do Mainframe  
**Colunas:**
- ID do cartão (Cartão de identificação)
- ID da disposição (disp_id)
- Tipo
- Data e hora de emissão (data_emitidahora)

## Conta

**Fonte:** Sistema de originação de conta  
**Formato de Origem:** Arquivo de texto - do Mainframe  
**Colunas:**
- ID da conta (ID_da_conta)
- ID da filial (ID_da_filial)
- Frequência
- Data de criação

## Banco Geral

**Fonte:** Banco de Dados de Disposições  
**Formato de Origem:** Arquivo de texto - do Mainframe  
**Colunas:**
- ID da disposição (disp_id)
- ID do Cliente
- ID da conta (ID_da_conta)
- Tipo

## Web Analytics

**Fonte:** Google Analytics  
**Formato de Origem:** JSON com campos aninhados  
**Colunas:**
- ID do Cliente
- Número de visita
- ID da visita
- Hora de início da visita
- Data
- Totais
- Fonte de tráfego
- Dispositivo
- GeoRede
- Dimensões personalizadas
- Exitos
- ID completo do visitante (fullVisitorId)
- ID do usuário

## Mapa de Visitantes Web

**Fonte:** Mapear visitantes da web para client_id  
**Formato de Origem:** Arquivo de texto  
**Colunas:**
- Hash de ID de visitante
- ID do Cliente

## Histórico de Compras

**Fonte:** Vendas no Varejo - Pedidos  
**Formato de Origem:** Arquivo CSV do aplicativo SaaS  
**Colunas:**
- ID da linha (id da linha)
- ID do pedido (id_pedido)
- Data do pedido (data do pedido)
- Data chave (data_chave)
- Nome de contato (nome de contato)
- País (país)
- Cidade (cidade)
- Região (região)
- Sub-região (sub-região)
- Cliente
- ID do Cliente
- Indústria (indústria)
- Segmento
- Produtos
- Licença
- Vendas
- Quantidade
- Desconto
- Lucro

---

Este documento fornece uma visão geral das fontes de dados utilizadas no workshop do AWS Builders Women's Edition 2024, destacando as principais colunas e formatos de origem. Para mais detalhes sobre a arquitetura e os recursos provisionados, consulte os outros documentos neste repositório.

