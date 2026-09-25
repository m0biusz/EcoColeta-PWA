# EcoColeta — proposta PWA | Práticas Extensionistas IV

> **Estado:** Entrega 1 de modelagem. O PWA, a infraestrutura e o CI/CD descritos abaixo **ainda não foram implementados nem publicados**.

## Equipe
- João Eduardo Panissa

## Problema e objetivo
Dificuldade de consultar dias de coleta, ecopontos e avisos locais e de acompanhar ocorrências de descarte irregular. O PWA proposto facilitará acesso móvel sem instalação obrigatória, consulta por bairro e comunicação de problemas pela comunidade. Público: moradores e responsáveis pela gestão das informações de coleta.

## Escopo planejado
- Consultar a próxima coleta por bairro, avisos e pontos de descarte.
- Visualizar mapa e localização com consentimento.
- Após autenticação, registrar ocorrência com descrição, localização e foto e acompanhar estado.
- Perfis autorizados gerenciam coletas, ecopontos e avisos.
- Instalação PWA e cache somente de conteúdo público previamente consultado; ações de escrita dependem de rede.

## Arquitetura proposta
- **PWA:** React, TypeScript, Vite, manifesto e service worker.
- **Dados e identidade:** Supabase Auth, Data API/PostgreSQL com RLS e Storage com políticas por perfil.
- **Distribuição:** Vercel via integração Git; o navegador comunica diretamente com os serviços do Supabase.
- **CI:** GitHub Actions para lint, testes e build quando o projeto web for criado. Vercel gera previews em PR e produção após merge em `main` quando sua integração for ativada.
- Não colocar chave secreta/service role no navegador. URL e chave publicável só com políticas RLS apropriadas.

## Entrega 1: diagramas
1. [Diagrama UML de pacotes](docs/pratica-extensionista-iv/diagramas/01-pacotes.svg).
2. [Diagrama de implantação](docs/pratica-extensionista-iv/diagramas/02-implantacao.svg).
3. [Diagrama DevOps](docs/pratica-extensionista-iv/diagramas/03-devops.svg).

[PDF para entrega](docs/pratica-extensionista-iv/Entrega_1_EcoColeta_PWA.pdf) · [Decisões de infraestrutura](docs/pratica-extensionista-iv/infraestrutura.md).

## Próximos passos de execução
1. Confirmar responsáveis comunitários e dados reais de coletas.
2. Criar projeto Supabase e estrutura de tabelas, RLS e buckets; obter URL e chave publicável.
3. Desenvolver o PWA e verificar uso offline, acessibilidade, permissões e políticas de acesso.
4. Criar projeto Vercel e conectar o repositório; configurar raiz do projeto web, variáveis e branch de produção.
5. Adicionar workflow de CI funcional, testar previews e publicar só após validação.

### Histórico
Este repositório é exclusivo da proposta **EcoColeta PWA** para a Prática Extensionista IV. O projeto Android anterior permanece em outro repositório.
