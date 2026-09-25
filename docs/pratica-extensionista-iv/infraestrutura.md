# Infraestrutura proposta — EcoColeta PWA

**Escolha:** Vercel para os arquivos estáticos do PWA, Supabase Cloud para identidade, API, PostgreSQL e fotos, GitHub/GitHub Actions para código e integração contínua. Esta é uma decisão de arquitetura da Entrega 1, não uma declaração de recursos ativados.

| Alternativa | Avaliação para o projeto |
|---|---|
| Vercel + Supabase | Integração Git e ambientes de preview; PostgreSQL, autenticação e armazenamento gerenciados. Separação entre web e dados. |
| Netlify + Supabase | Alternativa viável de hospedagem estática, sem ganho determinante para esta proposta. |
| Firebase | Boa integração, mas o modelo principal de dados difere do PostgreSQL relacional escolhido para coletas, bairros e ocorrências. |
| AWS/Azure | Mais opções de infraestrutura, configuração e gestão acima da necessidade da primeira versão acadêmica. |
| Self-host | Exige provisionar servidor, TLS, backups, monitoramento, atualizações e disponibilidade pela equipe. |

**Ativação futura:** criar contas/projetos sob responsabilidade do grupo; provisionar projeto Supabase na região apropriada, tabelas, RLS, políticas de Storage e usuários; importar a pasta do PWA no Vercel, configurar URL e chave publicável no ambiente e testar Preview e Production. Não há conta ou serviço de nuvem verificado como ativo nesta entrega.

**Fluxo e segurança:** navegador → Vercel para frontend; navegador → Supabase por HTTPS para dados. RLS protege cada tabela exposta. Fotos de ocorrências em bucket privado com política de acesso; nunca publicar chaves privilegiadas. Migrações do banco versionadas e revisadas. Cache offline somente para conteúdo público, com estratégia de atualização definida durante a implementação.

## Referências técnicas (acesso em 25 set. 2026)
- MDN. Making PWAs installable: https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Guides/Making_PWAs_installable
- Vercel. Deploying Git Repositories: https://vercel.com/docs/git
- Supabase. Row Level Security: https://supabase.com/docs/guides/database/postgres/row-level-security
- Supabase. API keys: https://supabase.com/docs/guides/getting-started/api-keys
- GitHub. Creating an example workflow: https://docs.github.com/en/actions/tutorials/create-an-example-workflow
