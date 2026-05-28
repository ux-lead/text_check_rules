# tone.md
# Tom de voz e princípios (robusto) . v1.0
# Uso: arquivo de referência e também base para regras executáveis no plugin.
# Convenção: regras em REGRAS (lint) são parseáveis.

## PRINCIPIOS
- Clareza antes de personalidade. Personalidade só aparece depois que a mensagem ficou inequívoca.
- Humano e respeitoso. Sem infantilizar, sem ironia, sem deboche.
- Confiança calma. Sem alarmismo, sem pressão artificial, sem exageros.
- Responsabilidade do sistema. Evite culpar a pessoa por erros do produto.
- Inclusivo. Linguagem acessível, sem termos capacitistas, sem estereótipos.
- Economia de palavras. Menos é mais, desde que não falte orientação.

## TOM
- Voz ativa e direta.
- Frases curtas (ideal: até 90 caracteres por sentença; acima disso, considere quebrar).
- Preferir verbos concretos (ver, salvar, enviar, continuar).
- Evitar “textão” em UI. Se o assunto é complexo, mover para ajuda/FAQ.

## PADROES POR CONTEXTO
### button
- Verbo no imperativo.
- 1 a 3 palavras.
- Evitar “OK” como ação principal (use verbo específico).
- Evitar negações confusas (ex.: “Não cancelar”).

### label
- Nome do campo, sem ponto final.
- Evitar dois-pontos.
- Evitar instruções no label (instruções vão no helper).

### helper
- Uma frase curta com formato, exemplo, limite ou regra.
- Não repetir o label.
- Quando possível, inclua exemplo (Ex.:).

### error
- 1) O que aconteceu (sem jargão). 2) O que fazer agora.
- Não culpar a pessoa.
- Se existir, sugerir caminho alternativo (ex.: “Tente novamente” ou “Voltar”).

### success
- Confirmar o resultado e, quando existir, o próximo passo.
- Evitar comemoração excessiva.

### empty_state
- Dizer o que está vazio.
- Dizer como preencher (ação).

### notification/toast
- Curto. Sem parágrafos.
- Se for crítico, direcionar para tela com detalhes.

## LINGUAGEM E ACESSIBILIDADE
- Evite siglas sem explicação quando o público não for técnico.
- Evite metáforas que exigem repertório específico.
- Prefira termos concretos e previsíveis.
- Evite ambiguidade temporal (“hoje/amanhã”) em mensagens persistentes.

## REGRAS (lint)
- id: tone_no_sarcasm_interjections
  severity: warn
  pattern: /\b(opss+|oops+|aff|kkk+|rsrs+|haha+|tá\s*de\s*brincadeira|só\s*que\s*não)\b/i
  message: Evite sarcasmo, deboche ou interjeições em UI. Prefira tom neutro e claro.
  suggestions:
    - "Certo. Vamos resolver isso."
    - "Tudo bem. Vamos ajustar."

- id: tone_no_fake_urgency
  severity: warn
  pattern: /\b(corre|agora\s*mesmo|última\s*chance|imperdível|só\s*hoje|não\s*perca)\b/i
  message: Evite urgência artificial. Use prazo real quando necessário.
  suggestions:
    - "Disponível até {data}."
    - "Oferta válida por tempo limitado."

- id: tone_avoid_blame_user
  severity: error
  pattern: /\b(você\s*(errou|digitou\s*errado|fez\s*errado)|culpa\s*sua|sua\s*culpa)\b/i
  message: Evite culpar a pessoa. Descreva o problema e o próximo passo.
  suggestions:
    - "Não foi possível validar as informações. Revise e tente novamente."
    - "Confira os dados e tente novamente."

- id: tone_avoid_aggressive_allcaps
  severity: warn
  pattern: /\b[A-ZÁÉÍÓÚÇ]{4,}\b/
  message: Evite palavras inteiras em CAIXA ALTA. Pode soar agressivo.
  suggestions:
    - "Use caixa normal e destaque só o essencial."

- id: tone_limit_exclamation
  severity: info
  pattern: /!/
  message: Evite exclamações em fluxos críticos. Prefira tom calmo.
  fix: remove_exclamation

- id: tone_avoid_many_exclamations
  severity: warn
  pattern: /!{2,}/
  message: Evite múltiplas exclamações.
  fix: remove_exclamation

- id: tone_avoid_absolute_promises
  severity: warn
  pattern: /\b(100%|garantido|perfeito|sempre|nunca|infalível)\b/i
  message: Evite promessas absolutas. Prefira linguagem precisa.
  suggestions:
    - "Geralmente"
    - "Na maioria dos casos"

- id: tone_avoid_technical_jargon
  severity: warn
  pattern: /\b(404|500|timeout|stack\s*trace|null\s*pointer|exception|traceback)\b/i
  message: Evite jargão técnico. Traduza para linguagem comum.
  suggestions:
    - "Não foi possível concluir agora. Tente novamente."
    - "Estamos com instabilidade. Tente mais tarde."

- id: tone_avoid_anxiety_words
  severity: info
  pattern: /\b(urgente|imediatamente|grave|crítico|pânico)\b/i
  message: Evite termos que geram ansiedade. Use apenas quando for realmente necessário.
  suggestions:
    - "Importante"
    - "Atenção"

- id: tone_sentence_too_long
  severity: info
  pattern: /^.{161,}$/
  message: Texto muito longo para UI. Considere quebrar ou mover detalhes para ajuda.
  suggestions:
    - "Divida em frases curtas."
    - "Mova detalhes para uma tela de suporte."

- id: tone_avoid_emoji_excess
  severity: info
  pattern: /\uD83C[\uDF00-\uDFFF]|\uD83D[\uDC00-\uDFFF]|\uD83E[\uDC00-\uDFFF]/
  message: Emojis podem afetar clareza e acessibilidade. Use com parcimônia.
  suggestions:
    - "Remova o emoji ou mantenha apenas em contextos não críticos."
