# Imersão Fullcycle 18 - Sistema de Venda de Ingressos

![Imersão Full Stack && Full Cycle](https://events-fullcycle.s3.amazonaws.com/events-fullcycle/static/site/img/grupo_4417.png)



## Visão Geral

O sistema de venda de ingressos visa oferecer uma plataforma robusta para a compra e gestão de ingressos de eventos diversos. Utilizando tecnologias modernas como NestJS para o backend, Konk Manager API para gestão de eventos, Go para microserviços e Next.js para o frontend, todo o sistema será distribuído em containers Docker para facilitar a implantação e escalabilidade.

## Arquitetura Geral

### Componentes Principais

1. **Backend (NestJS):**
   - Responsável pela lógica de negócios, autenticação de usuários, gerenciamento de ingressos e integração com Konk Manager API.
   - Implementará APIs RESTful para comunicação com o frontend.

2. **Konk Manager API:**
   - API externa para gestão de eventos, localizações e disponibilidade de ingressos.
   - Integração bidirecional para sincronização de dados de eventos e ingressos.

3. **Frontend (Next.js):**
   - Interface do usuário para navegação, seleção de eventos, compra de ingressos e visualização de ingressos adquiridos.
   - Utilizará renderização do lado do cliente (CSR) para uma experiência de usuário fluida e interativa.

4. **Microserviços (Go):**
   - Componentes independentes para funções específicas, como processamento de pagamentos, geração de ingressos eletrônicos, etc.
   - Comunicação via gRPC para alta performance e baixa latência entre serviços.

### Infraestrutura e Deploy

- Todos os componentes serão encapsulados em containers Docker.
- Orquestração de containers utilizando Docker Compose para desenvolvimento e Kubernetes para produção.
- Utilização de balanceamento de carga para distribuição de tráfego entre os containers.

## Detalhamento Técnico

### Backend (NestJS)

- **Módulos:**
  - `UserModule`: Gerenciamento de usuários e autenticação com JWT.
  - `EventModule`: Integração com Konk Manager API para sincronização de eventos e gerenciamento de ingressos.
  - `TicketModule`: Venda de ingressos, reserva e emissão de ingressos eletrônicos.
  - `PaymentModule`: Integração com serviços de pagamento.

- **Banco de Dados:**
  - Utilização de PostgreSQL para armazenamento de dados estruturados.
  - Redis para caching de dados frequentemente acessados e controle de sessões.

### Frontend (Next.js)

- **Páginas:**
  - `Index`: Lista de eventos e navegação principal.
  - `EventDetails`: Detalhes do evento e seleção de ingressos.
  - `Checkout`: Processo de pagamento e confirmação de compra.

- **Componentes:**
  - Integração com Konk Manager API para listar eventos disponíveis e informações de ingressos.
  - Uso de componentes React para modularização e reutilização de código.

### Microserviços (Go)

- **Serviços:**
  - `PaymentService`: Processamento de pagamentos utilizando serviços como Stripe.
  - `TicketService`: Geração e emissão de ingressos eletrônicos.

- **Comunicação:**
  - Protocolo gRPC para chamadas entre serviços.
  - Monitoramento de desempenho utilizando Prometheus e Grafana.

### Integração e Testes

- Testes unitários e de integração utilizando Jest (para NestJS) e Go testing (para Go).
- Integração contínua utilizando GitHub Actions para automação de builds, testes e deployment.

## Considerações de Segurança

- Autenticação baseada em JWT (JSON Web Tokens) para segurança de sessões.
- Validar e sanitizar entrada de dados para prevenir ataques de injeção SQL e XSS.
- Monitoramento de logs e auditoria de acesso para detectar atividades suspeitas.

## Escalabilidade e Desempenho

- Escalabilidade horizontal dos containers Docker utilizando Kubernetes para balanceamento de carga.
- Utilização de caches distribuídos para minimizar consultas ao banco de dados e melhorar o desempenho geral do sistema.

## Conclusão

O sistema de venda de ingressos oferece uma solução completa e escalável para gerenciamento de eventos e compra de ingressos. Utilizando tecnologias avançadas como NestJS, Konk Manager API, Go e Next.js, combinadas com containers Docker para distribuição eficiente, o sistema está preparado para lidar com altas demandas e proporcionar uma excelente experiência ao usuário final.

---

As instruções de instalações estão no README.md de cada projeto.

---