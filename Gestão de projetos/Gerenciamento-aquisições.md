# Gerenciamento das Aquisições — Projeto FieldOps

> Elaborado conforme documentação do projeto disponível em https://glaucotodesco.notion.site/Projeto-FieldOps-3af5d52a81f580c0b92ec261c686abb4
---

## Tabela de Aquisições

| ID | Cód. WBS/EAP | Item a ser adquirido | Urgência | Motivo da Decisão de Compra | Fornecedores potenciais | Qtde | Custo unitário | Custo total | Previsão de entrega | Observações |
|:--:|:------------:|----------------------|:--------:|----------------------------|------------------------|:----:|:--------------:|:-----------:|:-------------------:|-------------|
| 1 | 1.1 | Horas de desenvolvimento — Backend (API Spring Boot) | 5 — Muito Alta | Implementação da API REST com autenticação JWT, CRUDs, regras de negócio, sincronização e revisão. Componente central sem o qual nenhum fluxo funciona. | Equipe interna (1 dev backend) | 80 h | R$ 25,00/h | R$ 2.000,00 | Sprints 1–14 | Estimativa baseada em 16 semanas × 5 h/semana de projeto. Valor de referência para hora de dev júnior acadêmico. |
| 2 | 1.1 | Horas de desenvolvimento — Mobile (Expo / React Native) | 5 — Muito Alta | Implementação do aplicativo do técnico: login, checklist dinâmico, câmera, QR Code, GPS, SQLite, outbox e sincronização offline. Frente mais complexa do projeto. | Equipe interna (2 devs mobile) | 160 h | R$ 25,00/h | R$ 4.000,00 | Sprints 1–16 | 2 desenvolvedores × 80 h cada. Inclui build Android via EAS. |
| 3 | 1.1 | Horas de desenvolvimento — Frontend Web (React + Vite) | 4 — Alta | Implementação da interface administrativa: login, CRUD de cadastros, construtor de modelos, planejamento de inspeções, acompanhamento e revisão. | Equipe interna (2 devs frontend) | 120 h | R$ 25,00/h | R$ 3.000,00 | Sprints 1–14 | 2 desenvolvedores × 60 h cada. Telas de inspeção e revisão são as mais críticas e ainda ausentes. |
| 4 | 1.2 | Horas de gestão, documentação e QA | 4 — Alta | Manutenção do backlog, documentação no Notion e GitHub, análise de conformidade, critérios de aceitação, testes funcionais e preparação da demonstração final. | Equipe interna (1 PO / QA) | 48 h | R$ 25,00/h | R$ 1.200,00 | Sprints 1–16 | 3 h/semana × 16 semanas. Inclui atualização da análise de conformidade a cada sprint. |
| 5 | 1.3 | Hospedagem da API Spring Boot em nuvem | 4 — Alta | A API precisa de URL pública para que o app mobile (dispositivo físico) e o frontend se conectem na demonstração final. Free tiers têm limitações de sleep e recursos. | Render (free / US$ 7/mês), Railway (free / US$ 5/mês), Fly.io (free) | 1 | R$ 0,00 – R$ 40,00/mês | R$ 0,00 – R$ 80,00 | Sprint 14 | Free tier pode ser suficiente para a demo. Se o sleep comprometer a avaliação, upgrade recomendado (~R$ 40/mês × 2 meses). |
| 6 | 1.3 | Banco de dados PostgreSQL em nuvem | 4 — Alta | Necessário para ambiente de homologação e demonstração. H2 em memória (dev) não persiste dados entre restarts nem é acessível externamente. | Supabase (free: 500 MB), Neon (free: 3 GB), Render PostgreSQL (US$ 7/mês) | 1 | R$ 0,00 – R$ 40,00/mês | R$ 0,00 – R$ 80,00 | Sprint 12 | Free tier de Supabase suficiente para MVP. Custo pago previsto apenas se limite for atingido. |
| 7 | 1.3 | Storage de objetos para evidências (fotos) | 3 — Média | Fotos capturadas em campo não podem ficar em pasta local em produção. Banco armazena apenas metadados; arquivos exigem storage externo (spec seção 11.8). Upload máx. 10 MB/arquivo. | Cloudinary (free: 25 GB), Supabase Storage (free: 1 GB), AWS S3 (free tier) | 1 | R$ 0,00 – R$ 15,00/mês | R$ 0,00 – R$ 30,00 | Sprint 9 | Cloudinary free tier (25 GB) suficiente para MVP. Custo pago improvável neste volume. |
| 8 | 1.4 | Conta Expo EAS Build — build Android | 4 — Alta | Necessária para gerar o .apk para instalação em dispositivo físico na demonstração, exigido pelo DoD do MVP (spec seção 18.6). | Expo EAS (free: 30 builds/mês; Production: US$ 29/mês) | 1 | R$ 0,00 | R$ 0,00 | Sprint 15 | 30 builds/mês gratuitos suficientes para o volume do projeto. |
| 9 | 1.4 | Dispositivo Android físico para testes | 5 — Muito Alta | Câmera, QR Code, GPS, modo avião e sincronização offline não podem ser validados apenas no emulador. Android é plataforma obrigatória de validação (spec seção 1.8). | Aparelhos dos próprios integrantes | 1 | R$ 0,00 | R$ 0,00 | Sprint 1 | Necessário ao menos 1 dispositivo Android 10+ disponível para os Sprints 9–16. Verificar na Sprint 1. |
| 10 | 1.5 | Ferramentas de desenvolvimento (IDEs, Node.js, JDK, Figma, Postman) | 3 — Média | Ferramentas necessárias para o desenvolvimento diário: IntelliJ/VS Code para código, Android Studio para mobile, Figma para protótipos e Postman para testes de API. | JetBrains, Microsoft, Google, Figma, Postman (gratuitos / licença edu) | 8 | R$ 0,00 | R$ 0,00 | Sprint 1 | Todas gratuitas. JetBrains oferece licença Ultimate gratuita para estudantes via jetbrains.com/student. |

---

## Resumo de Custos

| Categoria | Custo mínimo | Custo máximo estimado |
|-----------|:------------:|:---------------------:|
| Horas de desenvolvimento — Backend | R$ 2.000,00 | R$ 2.000,00 |
| Horas de desenvolvimento — Mobile | R$ 4.000,00 | R$ 4.000,00 |
| Horas de desenvolvimento — Frontend Web | R$ 3.000,00 | R$ 3.000,00 |
| Horas de gestão, documentação e QA | R$ 1.200,00 | R$ 1.200,00 |
| Hospedagem da API em nuvem | R$ 0,00 | R$ 80,00 |
| Banco de dados em nuvem | R$ 0,00 | R$ 80,00 |
| Storage de evidências | R$ 0,00 | R$ 30,00 |
| EAS Build + dispositivo + ferramentas | R$ 0,00 | R$ 0,00 |
| **TOTAL** | **R$ 10.200,00** | **R$ 10.390,00** |

---

## Legenda WBS/EAP

| Código | Descrição |
|--------|-----------|
| 1.1 | Desenvolvimento de software |
| 1.2 | Gestão e documentação |
| 1.3 | Infraestrutura de nuvem |
| 1.4 | Build, dispositivos e distribuição |
| 1.5 | Ferramentas e licenças |

---

## Notas

- O custo dominante do projeto é o **capital humano** — 408 horas de trabalho da equipe ao longo de 16 semanas.
- Os serviços de nuvem são acessíveis via free tier para o MVP, com custo potencial máximo de **R$ 190,00** caso os limites gratuitos sejam insuficientes para a demonstração final.
- A escala de urgência segue o padrão: **1 — Muito Baixa | 2 — Baixa | 3 — Média | 4 — Alta | 5 — Muito Alta**.
- Documento elaborado com base na documentação do Notion (22 subpáginas), código-fonte dos repositórios e artefatos disponíveis em outubro de 2026.
