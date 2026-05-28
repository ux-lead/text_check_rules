# copy.md
# Diretrizes de copy para produtos digitais (robusto) . v1.0
# Convenção: regras em REGRAS (lint) são parseáveis.
# Observação: regras de contexto (button/error/helper/label) podem ser aplicadas via heurística do plugin.

## PRINCIPIOS DE UX WRITING
- Comece pelo objetivo: o que a pessoa precisa fazer agora.
- Seja específico: “Salvar alterações” é melhor que “OK”.
- Antecipe dúvidas: formato, limite, prazo, e o “por quê” quando necessário.
- Seja consistente: termos, capitalização, padrões de erro, números e datas.
- Reduza carga cognitiva: uma instrução por frase.

## PADROES RECOMENDADOS
### Botões
- Verbo no imperativo: "Continuar", "Salvar", "Enviar".
- Ação destrutiva com clareza: "Excluir", "Remover".
- Evite "Sim/Não" como ação principal em modais. Prefira ações: "Cancelar", "Confirmar".

### Erros
- Estrutura: "Não foi possível {ação}. {próximo passo}."
- Se for validação: "Informe {campo} para continuar."
- Se for sistema: "Estamos com instabilidade. Tente mais tarde."

### Campos e formulários
- Label: nome do campo.
- Helper: exemplo e formato. Ex.: "Ex.: nome@dominio.com".
- Placeholder não substitui label.

### Datas e números
- Evite ambiguidade: preferir DD/MM/AAAA em pt-BR.
- Valores: "R$ 1.234,56".
- Evite datas relativas em mensagens persistentes.

### Microcópias úteis
- Estados: carregando, vazio, sucesso, falha.
- Confirmações: explique impacto quando existir (ex.: “Isso remove acesso”).

## REGRAS (lint)
# Ações e CTAs
- id: copy_no_click_here
  severity: error
  pattern: /\b(clique\s*aqui|click\s*here|toque\s*aqui|tap\s*here)\b/i
  message: Evite "clique aqui". Use uma ação contextual.
  suggestions:
    - "Ver detalhes"
    - "Abrir configurações"
    - "Saiba mais"

- id: copy_button_no_ok_generic
  severity: warn
  pattern: /^(ok|okay|ok\.)$/i
  message: Evite botão genérico "OK". Use um verbo específico.
  suggestions:
    - "Entendi"
    - "Continuar"
    - "Salvar"

- id: copy_button_no_yes_no
  severity: info
  pattern: /^(sim|não|yes|no)$/i
  message: Em botões, prefira ações específicas em vez de Sim/Não.
  suggestions:
    - "Confirmar"
    - "Cancelar"

- id: copy_avoid_now_word
  severity: info
  pattern: /\b(agora|já)\b/i
  message: Evite "agora/já" sem necessidade. Pode soar pressionador.
  suggestions:
    - "Continue"
    - "Concluir"

# Pontuação e espaços
- id: copy_no_double_space
  severity: info
  pattern: / {2,}/
  message: Há espaços duplicados. Normalize espaços.
  fix: normalize_spaces

- id: copy_no_space_before_punct
  severity: info
  pattern: /\s+([,.;:!?])/g
  message: Remova espaço antes de pontuação.
  fix: remove_space_before_punct

- id: copy_reduce_many_question_marks
  severity: warn
  pattern: /\?{2,}/
  message: Evite múltiplas interrogações.
  fix: reduce_question_marks

- id: copy_avoid_many_ellipses
  severity: warn
  pattern: /\.{4,}|…{2,}/
  message: Evite reticências excessivas. Prefira texto objetivo.
  suggestions:
    - "Finalize com ponto e seja específico."

- id: copy_avoid_multiple_punct
  severity: warn
  pattern: /([!?.,])\1{1,}/
  message: Evite pontuação repetida.
  suggestions:
    - "Use apenas um sinal de pontuação."

# Linguagem clara
- id: copy_avoid_generic_error
  severity: error
  pattern: /\b(erro\s*inesperado|algo\s*deu\s*errado|ocorreu\s*um\s*erro)\b/i
  message: Erro genérico. Diga o que aconteceu e o que fazer agora.
  suggestions:
    - "Não foi possível concluir {ação}. Tente novamente."
    - "Não foi possível carregar {conteúdo}. Verifique sua conexão."

- id: copy_avoid_passive_voice_hint
  severity: info
  pattern: /\b(foi\s*feito|será\s*realizado|está\s*sendo\s*processado)\b/i
  message: Considere voz ativa para maior clareza.
  suggestions:
    - "Processando"
    - "Estamos processando"  # use apenas se necessário

- id: copy_avoid_company_jargon
  severity: warn
  pattern: /\b(solicitação\s*indeferida|divergência\s*cadastral|inconsistência\s*nos\s*dados|pendência\s*cadastral)\b/i
  message: Evite juridiquês/jargão. Traduza para linguagem comum.
  suggestions:
    - "Não foi possível confirmar seus dados. Revise e tente novamente."
    - "Encontramos um problema com suas informações. Revise e tente novamente."

- id: copy_avoid_threatening_language
  severity: warn
  pattern: /\b(sua\s*conta\s*será\s*(cancelada|bloqueada)|você\s*perderá)\b/i
  message: Evite linguagem ameaçadora. Explique motivo e próximos passos.
  suggestions:
    - "Para manter sua conta segura, precisamos confirmar {algo}."
    - "Atualize {algo} para continuar usando o serviço."

- id: copy_avoid_caps_lock_emphasis
  severity: warn
  pattern: /\b(IMPORTANTE|ATENÇÃO|URGENTE)\b/
  message: Evite ênfase em caixa alta. Use estrutura e hierarquia.
  suggestions:
    - "Importante: ..."
    - "Atenção: ..."

# Consistência de termos
- id: copy_avoid_login_logar
  severity: warn
  pattern: /\b(logar|logado|logada|login|log\s*in)\b/i
  message: Padronize termos. Prefira "entrar" e "acessar" conforme glossário.
  suggestions:
    - "Entrar"
    - "Acessar"

- id: copy_avoid_placeholder_as_label
  severity: info
  pattern: /\b(digite\s*seu|digite\s*sua|insira\s*seu|insira\s*sua)\b/i
  message: Evite instruções genéricas repetidas. Prefira formato e exemplo no helper.
  suggestions:
    - "Ex.: {exemplo}"
    - "Use o formato {exemplo}."

# Labels e títulos
- id: copy_label_no_trailing_punct
  severity: info
  pattern: /[:.]\s*$/
  message: Em labels, evite finalizar com ponto ou dois-pontos.
  suggestions:
    - "Remova a pontuação final."

- id: copy_title_case_mixed_warning
  severity: info
  pattern: /\b[A-Z][a-z]+([A-Z][a-z]+)+\b/
  message: Verifique consistência de capitalização (ex.: Title Case) conforme padrão do produto.
  suggestions:
    - "Padronize para frase normal ou Title Case, de forma consistente."

# Datas, números e moeda (pt-BR)
- id: copy_currency_brl_format
  severity: info
  pattern: /\bR\$\s?\d+(\.\d{3})*(,\d{2})?\b/
  message: Verifique formato BRL. Ex.: R$ 1.234,56.
  suggestions:
    - "R$ 1.234,56"

- id: copy_date_ambiguous_mmdd
  severity: warn
  pattern: /\b\d{1,2}\/\d{1,2}\/\d{2,4}\b/
  message: Verifique se a data está no padrão pt-BR (DD/MM/AAAA).
  suggestions:
    - "Ex.: 14/02/2026"

- id: copy_relative_dates
  severity: info
  pattern: /\b(hoje|amanhã|ontem)\b/i
  message: Evite datas relativas em mensagens persistentes. Prefira data explícita quando necessário.
  suggestions:
    - "Use data real (DD/MM/AAAA) quando o texto for persistente."

# Acessibilidade e inclusão
- id: copy_avoid_capacitist_terms
  severity: warn
  pattern: /\b(c*ego|ceguinho|surdo\s*mudo|retardado|débil|louco|maluco)\b/i
  message: Evite termos capacitistas ou ofensivos. Use linguagem respeitosa.
  suggestions:
    - "Reescreva com respeito e objetividade."

- id: copy_avoid_gendered_defaults
  severity: info
  pattern: /\b(o\s*usuário|o\s*cliente)\b/i
  message: Considere linguagem mais inclusiva quando fizer sentido.
  suggestions:
    - "a pessoa"
    - "quem usa"

# Segurança e privacidade (clareza)
- id: copy_security_explain_action
  severity: info
  pattern: /\b(por\s*segurança)\b/i
  message: Quando possível, explique o que será verificado (sem expor detalhes sensíveis).
  suggestions:
    - "Para manter sua conta segura, vamos confirmar {algo}."

# Tamanho e densidade
- id: copy_too_long_for_ui
  severity: info
  pattern: /^.{181,}$/
  message: Texto muito longo para UI. Considere dividir ou mover detalhes para ajuda.
  suggestions:
    - "Divida em frases curtas."
    - "Mova detalhes para uma tela de suporte."
