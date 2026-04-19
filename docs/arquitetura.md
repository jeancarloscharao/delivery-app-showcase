# 🧠 Arquitetura — Delivery App

## 📌 Visão geral

O Delivery App é uma aplicação web monolítica baseada em Laravel que combina e-commerce, gestão de pedidos e logística de entrega.

A arquitetura integra frontend público e painel administrativo em um único backend, com suporte a pagamentos e cálculo de entrega. 

---

## 🎯 Objetivos arquiteturais

* suportar vendas online em tempo real
* calcular taxas de entrega automaticamente
* integrar pagamentos digitais
* gerenciar pedidos e operação
* permitir evolução do sistema

---

## 🧩 Arquitetura do sistema

### 🌐 Frontend

* site público em Blade
* carrinho baseado em sessão
* checkout dinâmico
* acompanhamento de pedidos

---

### 🛠️ Backend

* Laravel como núcleo da aplicação
* Filament como painel administrativo
* controle de pedidos e produtos
* integração com serviços externos

---

## 🏗️ Arquitetura em camadas

### Camada de apresentação

* site público
* painel administrativo

---

### Camada de aplicação

* fluxo de checkout
* processamento de pedidos
* cálculo de taxa de entrega

---

### Camada de domínio

* Order (pedido)
* Product (produto)
* Extra (acompanhamento)
* Customer (cliente)
* Deliverer (entregador)

---

### Camada de dados

* persistência de pedidos
* histórico de status
* configuração de entrega

---

## 📍 Cálculo de entrega

* integração com Google Distance Matrix
* cálculo baseado em:

  * distância mínima
  * valor por km
  * distância máxima permitida
* bloqueio automático fora da área

---

## 💰 Integração de pagamento

* Mercado Pago (PIX)
* geração de QR Code
* webhook para atualização de pagamento
* atualização automática do status do pedido

---

## 🔄 Fluxo de pedido

1. cliente adiciona produtos
2. escolhe endereço
3. sistema calcula taxa
4. pedido é criado
5. pagamento é iniciado
6. webhook confirma pagamento
7. pedido evolui de status

---

## 📦 Gestão de pedidos

* estados controlados:

  * pendente
  * em preparo
  * em entrega
  * entregue
  * cancelado
* ações no painel administrativo

---

## 🔐 Controle de acesso

* autenticação Laravel
* roles com Spatie:

  * admin
  * cliente

---

## 📊 Dashboard

* métricas de vendas
* ticket médio
* distribuição por status
* análise de faturamento

---

## 📈 Escalabilidade

A arquitetura permite evolução para:

* multi-restaurantes
* integração com apps mobile
* otimização de rotas
* múltiplos meios de pagamento

---

## 💡 Decisões arquiteturais

* arquitetura monolítica para simplicidade
* uso de serviços externos para cálculo e pagamento
* carrinho baseado em sessão
* painel administrativo integrado

---

## 🧾 Conclusão

O Delivery App foi projetado como uma solução completa de e-commerce para delivery, integrando vendas, logística e pagamentos em uma única plataforma, com capacidade de evolução para cenários mais complexos.
