# Hiron · LP Diagnóstico gratuito · Marketing SP (Meta Ads)

Conteúdo do pacote:
- `index.html` — LP completa em arquivo único (fotos e logos embutidos). Formulário RD Station `lp-gerente-marketing-growth-b2c-meta-ads-a3ced85ec710bb472501` já instalado.
- `vercel.json` — mesmo padrão das outras LPs da Hiron (subir a pasta na Vercel ou em qualquer hospedagem estática).

## Meta Pixel
Já instalado: Pixel "Hiron · Site", ID 1149134137863926 (portfólio Hiron Talent). Para trocar no futuro:
1. No Gerenciador de Eventos do Meta, copie o **ID do Pixel** (só números).
2. Abra `index.html`, procure `SEU_PIXEL_ID` (linha ~20) e troque pelo ID:
   `window.HIRON_PIXEL_ID = '123456789012345';`
3. Publique e teste com a extensão **Meta Pixel Helper** ou em Eventos de teste.

Enquanto o ID for `SEU_PIXEL_ID`, o Pixel não carrega e os eventos só aparecem no console do navegador (`[Pixel placeholder]`).

## Eventos instalados
| Evento | Quando dispara |
|---|---|
| PageView | ao abrir a página |
| ViewContent | quando o formulário aparece na tela (1x por sessão) |
| **Lead** | só quando o RD Station confirma o envio do formulário (resposta 2xx da API do RD; reserva: mensagem de sucesso na tela). 1x por sessão, com `eventID` para deduplicar com a API de Conversões |
| Contact | clique no botão de WhatsApp |

O Lead leva o parâmetro `movimento` (Salário maior / Cargo acima / Empresa diferente) quando a pessoa escolhe um dos cards do topo.

**Campanha:** objetivo Cadastros, local de conversão Site, evento de conversão **Lead**.

## Recomendações
- No RD Station, deixe o formulário com **mensagem de sucesso** (sem redirecionar), para o Lead ser registrado antes de sair da página. Se preferir redirecionar para uma página de obrigado, instale o Lead nela.
- Instale também o **código de monitoramento do RD** (loader.js) para os leads chegarem com a origem/UTM.
- Parâmetros de URL no anúncio:
  `utm_source=meta&utm_medium=paid_social&utm_campaign=gc_marketing_sp_2027&utm_content={{ad.name}}`
- A página tem `noindex` (é LP de mídia paga). Remova se quiser que o Google indexe.
