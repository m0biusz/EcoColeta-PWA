# Infraestrutura proposta — EcoColeta PWA

**Escolha:** Vercel para os arquivos estáticos do PWA, Supabase Cloud para identidade, API, PostgreSQL e fotos, GitHub/GitHub Actions para código e integração contínua. Esta é uma decisão de arquitetura da Entrega 1, não uma declaração de recursos ativados.

| Alternativa | Avaliação para o projeto |
|---|---|
| Vercel + Supabase | Integração Git e ambientes de preview; PostgreSQL, autenticação e armazenamento gerenciados. Separação entre web e dados. |
| Netlify + Supabase | Alternativa viável de hospedagem estática, sem ganho determinante para esta proposta. |
| Firebase | Boa integração, mas o modelo principal de dados difere do PostgreSQL relacional escolhido para coletas, bairros e ocorrências. |
| AWS/Azure | Mais opções de infraestrutura, configuração e gestão acima da necessidade da primeira versão acadêmica. |
| Self-host | Exige provisionar servidor, TLS, backups, monitoramento, atualizações e disponibilidade pela equipe. |

**Situação de ativação:** o usuário GitHub e o repositório do projeto estão ativos. Não há projeto Supabase ou Vercel verificado como ativo nesta entrega. Isso permanece uma pendência do item 5 do enunciado. Criar projeto Supabase na região apropriada, tabelas, RLS e políticas de Storage; criar projeto Vercel conectado ao GitHub quando houver um build PWA; configurar URL e chave publicável no ambiente; testar Preview e Production. Registrar os identificadores dos projetos e a evidência da ativação antes da entrega definitiva, sem divulgar credenciais.

**Fluxo e segurança:** navegador → Vercel para frontend; navegador → Supabase por HTTPS para dados. RLS protege cada tabela exposta. Fotos de ocorrências em bucket privado com política de acesso; nunca publicar chaves privilegiadas. Migrações do banco versionadas e revisadas. Cache offline somente para conteúdo público, com estratégia de atualização definida durante a implementação.

**Escopo técnico:** avisos serão apresentados no aplicativo. Lembretes automáticos fora do navegador requerem serviço de push/agendamento e permissão específica, a definir em etapa posterior. Dados e funcionalidades do protótipo Android não comprovam implantação do PWA. Os endereços de API e credenciais citados em materiais anteriores são exemplos ou pertencem ao projeto Android e não são reutilizados aqui.

## Referências técnicas (acesso em 25 set. 2026)
- MDN. Making PWAs installable: https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Guides/Making_PWAs_installable
- Vercel. Deploying Git Repositories: https://vercel.com/docs/git
- Supabase. Row Level Security: https://supabase.com/docs/guides/database/postgres/row-level-security
- Supabase. API keys: https://supabase.com/docs/guides/getting-started/api-keys
- GitHub. Creating an example workflow: https://docs.github.com/en/actions/tutorials/create-an-example-workflow
