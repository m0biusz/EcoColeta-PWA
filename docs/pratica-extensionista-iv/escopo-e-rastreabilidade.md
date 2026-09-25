# Base do EcoColeta e adaptação para PWA

Esta modelagem usa o estudo de Desenvolvimento Mobile, a apresentação EcoColeta e a documentação técnica Android fornecidos por João Eduardo Panissa. O aplicativo Android anterior demonstrou telas com **dados simulados**; não possui autenticação ou envio real de fotos. O PWA é um projeto novo, em fase de modelagem.

| Requisitos do estudo anterior | Tratamento na arquitetura PWA |
|---|---|
| RF01 cadastro e autenticação | Supabase Auth; perfis e autorização com políticas RLS a implementar. |
| RF02–RF05 região, horários, áreas no mapa e ecopontos | Modelos Área/Bairro, Coleta e Ponto de descarte; consultas por casos de uso e API; permissão de localização. Serviço cartográfico a escolher na implementação. |
| RF06 lembretes e comunicados | Avisos publicados para leitura no PWA; lembretes automáticos exigem serviço de push e agendamento não incluído na primeira implantação. |
| RF07–RF10 e RF12 ocorrência, foto, localização, estado e histórico | Modelo Ocorrência/Status; fluxo Enviado → Recebido → Em análise → Em atendimento → Resolvido; anexos previstos em Storage e dados protegidos por RLS. |
| RF11 comunicados do órgão responsável | Módulo Avisos; publicação somente por perfil autorizado. Não há integração ou parceria oficial confirmada. |

**PWA:** manifesto para instalação, service worker para cache de consulta pública e interface responsiva. Ocorrências, autenticação e dados novos dependem de internet. Geolocalização e avisos do navegador exigem consentimento e suporte do dispositivo. A solução não deve prometer horários oficiais antes de obter dados de uma fonte responsável.

**Público:** moradores de Videira/SC, comunidade piloto escolhida pelo autor, e administradores autorizados. Dados municipais e eventual parceria comunitária ainda devem ser confirmados; o material anterior não comprova validação com a prefeitura.
