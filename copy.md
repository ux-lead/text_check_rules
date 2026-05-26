# copy.md
# Diretrizes de Copy – Liquid Design System Bradesco (v1.0)
# Fonte: ZeroHeight – Seção Conteúdo
# Foco: padrões de UX Writing, formatação e lint para interface.

## PADROES

### Botões
# Ref: https://zeroheight.com/33af959d2/v/latest/p/04b4f1-botoes-e-links
- Botão: verbo + objeto (opcional). Ex.: "Acessar conta", "Continuar".
- Botão em tela de erro com alternativas: verbo no infinitivo. Ex.: "Tentar de novo".
- Botão em tela de erro sem alternativas: "Ok, entendi".
- Botão de acesso à conta: "Acessar" / "Acesso" / "Acesse" + complemento.
- Botão voltar ao topo: "Voltar ao topo" (apenas no fim da tela).
- Botão voltar para home: "Voltar ao início".
- Botão sair: "Sair" (sem complemento).
- Botão alterar dados: "Alterar" (não usar "Editar").
- Botão FAQ: "Tire suas dúvidas" / "Tirar dúvidas" / "Tenho dúvidas".
- Link FAQ isolado: "Dúvidas?".
- Link FAQ inline: "tire suas dúvidas por aqui".
- Link dentro da FAQ: "Saiba mais sobre o/a [produto/serviço]".
- Botão confirmação exclusão (título pergunta): "Sim, [verbo de ação do título]".
- Botão confirmação exclusão (título afirmação): "[Verbo no infinitivo] + [complemento]".
- Botão secundário de exclusão: "Fechar".

### Labels e campos
# Ref: https://zeroheight.com/33af959d2/v/latest/p/72100a-campos-de-dados
- Label: nome do campo, sem ponto-final, sem dois-pontos ao final.
- Endereço: CEP / Rua, avenida, alameda... / Número / Complemento / Bairro / Cidade / Estado.
- Telefone com título: label "celular" ou "telefone", placeholder "DDD + número".
- Telefone sem título: placeholder "celular" ou "telefone", helper "DDD + número".
- Datas – 1 campo: label com contexto, helper "De [data mín.] até [data máx.]".
- Datas – 2 campos: labels "De" e "Até", precedidos de título contextualizando.
- Valores: usar Text Field ou Slider.

### Campos de busca
# Ref: https://zeroheight.com/33af959d2/v/latest/p/860d5b-campos-de-busca
- Contexto autoexplicativo: "Buscar".
- Com categoria: "Buscar por [objeto]" ou "Buscar [objeto]".
- Legenda com exemplos: iniciar com "Ex.:".
- FAQ: "O que você procura?".

### Helper text (legenda)
# Ref: https://zeroheight.com/33af959d2/v/latest/p/72100a-campos-de-dados
- Instrução curta, sem repetir a label.
- Não iniciar com "Digite o seu" / "Insira o sua" — vá direto ao formato esperado.
- Helper text pode manter-se como feedback de erro se o erro decorre de descumprimento da instrução.

### Feedback de erro em campos
# Ref: https://zeroheight.com/33af959d2/v/latest/p/1810b5-feedback-de-erro-em-campos-de-dados
- Dado já cadastrado: "[Dado] já cadastrado/cadastrada em outra conta. Informe outro/outra pra continuar."
- Dado inválido (sem orientação no helper): "[Dado] inválido/inválida. Verifique e tente de novo."
- Dado inválido (com complemento): "[Dado] inválido/inválida. Verifique [complemento]."
- Orientação já no helper: manter mesmo texto como feedback de erro.
- Email formato: "O email deve ter o formato exemplo@email.com".
- Email conteúdo inválido: "Email inválido. Verifique e tente de novo."
- Emails diferentes: "Emails diferentes. Verifique e tente de novo."
- Campo obrigatório (dado na label): "Informe o/a [nome do dado]".
- Campo obrigatório (dado fora da label): "Informe o/a [nome do dado esperado]".

### Alertas e avisos
# Ref: https://zeroheight.com/33af959d2/v/latest/p/91a0a8-alertas-e-avisos
- Impacto direto: título "É importante saber".
- Impacto possível: título "É bom saber" ou "Vale saber".
- Tom informal/lembrete: título "Só pra avisar".

### Confirmação de exclusão ou recusa
# Ref: https://zeroheight.com/33af959d2/v/latest/p/994dd6-confirmacao-de-exclusao-ou-recusa
- Ação simples (reversível): "Quer [ação]?".
- Ação com consequência (irreversível): "Quer mesmo [ação]?".
- Duas modais: 1ª pergunta, 2ª afirmação (evitar duas perguntas seguidas).
- Texto de apoio: iniciar com "Ao fazer isso," + consequência.

### Aceites e preferências
# Ref: https://zeroheight.com/33af959d2/v/latest/p/38c240-aceites-e-preferencias
- Comunicações: "Concordo que o Bradesco fale comigo sobre minha conta e novidades neste [dado]" (sem "Eu").
- Não ver mais: "Não ver mais esta mensagem".
- Termos (com nome): "Li e concordo com o/a [nome do termo]".
- Termos (sem nome): "Li e concordo com os termos de uso".
- Termos (dentro da modal): "Li e concordo".
- Aceite automático: "Ao [verbo no infinitivo], você concorda com os termos e as condições".
- Nunca iniciar aceite com "Eu".
- Nunca usar ponto-final em checkbox.
- Nunca usar título antes de checkbox.

### Progressão de etapas
# Ref: https://zeroheight.com/33af959d2/v/latest/p/83f8bb-progressao-de-etapas
- Padrão: "Passo [número] de [número]".
- Não usar "Etapa [número] de [número]".

### Máscara de caracteres
# Ref: https://zeroheight.com/33af959d2/v/latest/p/533356-mascara-de-caracteres
- Usar "●" (bullet) por caractere oculto.
- Não se aplica ao componente Hide text (ex.: saldo).

### Anuidade de cartão
# Ref: https://zeroheight.com/33af959d2/v/latest/p/96fca6-anuidade-de-cartao-de-credito
- Texto corrido: "Anuidade por 12x de R$ 00,00".
- Com valor total: "Anuidade por R$ 000,00 em 12x de R$ 00,00".
- Tabela/componente: "12x de R$ 00,00" ou "12x de R$ 00,00 (R$ 000,00)".
- "x" em caixa-baixa, junto ao número, sem espaço.

### Switch de impressão digital (Android)
# Ref: https://zeroheight.com/33af959d2/v/latest/p/93535a-biometrias
- Switch: "Habilitar impressão digital".
- Modal: "Use a impressão digital pra [nome da jornada]".

## FORMATAÇÃO

### Números e cifras
# Ref: https://zeroheight.com/33af959d2/v/latest/p/389182-numeros-e-cifras
- Sempre usar algarismos (inclusive 0–10). Ex.: "3 dias úteis", "5 chances".
- A partir de 1 mil (institucional): "R$ 1 mil", "R$ 10 mil", "4 mil agências".
- Transacional com campos parametrizáveis: sempre numeral com casas decimais.
- Números de telefone: blocos com espaço, sem hífen, sem parênteses no DDD.
- Número ordinal: "1º titular", "2ª via".
- Se +2 valores na tela, padronize o ",00" (todos com ou todos sem).

### Moedas
# Ref: https://zeroheight.com/33af959d2/v/latest/p/46f946-moedas
- Símbolo + espaço + valor. Ex.: "R$ 1.234,56".
- Transacional: preferir o ",00".
- Comercial: possível retirar o ",00".
- BGS: usar sigla "BRL" (ISO 4217).

### Datas, dias e horários
# Ref: https://zeroheight.com/33af959d2/v/latest/p/1447a0-datas-dias-e-horarios
- Datas: numeral com barra e zero. Ex.: "05/01/2020". 1º dia do mês: ordinal "1º/03/2020".
- Dias da semana: por extenso. Intervalos úteis: "de segunda a sexta".
- Horários: numeral + "h". Ex.: "19h", "8h35". Duração: por extenso ("2 horas e 30 minutos").
- Intervalos: "De [início] a [fim]". Evitar "ontem", "este mês", "ano passado".
- Temporizador < 1h: "00:00". ≥ 1h: "00:00:00".

### Siglas
# Ref: https://zeroheight.com/33af959d2/v/latest/p/32e13d-siglas
- Significado por extenso na 1ª ocorrência: sigla primeiro, termo entre parênteses. Ex.: "FGC (Fundo Garantidor de Créditos)".
- Até 3 letras: tudo caixa-alta. 4+ pronunciadas separadamente: caixa-alta. 4+ como palavra: só inicial maiúscula.
- Plural: "CPFs" (sem apóstrofo). SMS: "Os SMS" (sem 's').
- S.A.: com pontos. Não usar "S/A" ou "SA".

### Abreviaturas
# Ref: https://zeroheight.com/33af959d2/v/latest/p/970794-abreviaturas
- Usar apenas em restrição de espaço (tabelas, listas, campos).
- Meses: jan. / fev. / mar. / abr. / mai. / jun. / jul. / ago. / set. / out. / nov. / dez.
- Valores monetários: bi (bilhões), mi (milhões), tri (trilhões).

### Símbolos e pontuação
# Ref: https://zeroheight.com/33af959d2/v/latest/p/09b368-simbolos-sinais-e-pontuacoes
- Aspas duplas para citações; aspas simples só dentro de outra citação.
- Asterisco: disclaimer no fim da peça. 2+: numerais sobrescritos.
- Barra oblíqua: sem espaços. Preferir "ou" quando tiver mesmo significado.
- Et cetera: "etc." (sem vírgula antes, sem reticências depois).
- Exclamação: máx. 1 em texto corrido. Não usar em botões transacionais.
- Ponto-final: NÃO usar em títulos, bullets, labels, endereços de site.
- Ponto-final: USAR em textos de apoio (quando +1 período).
- Meia-risca (–): para intercalar expressões. Não usar hífen (-) nem travessão (—).
- Parcelamento: "vezes" como padrão; "x" só em espaço extremamente reduzido.
- Pontuação em hiperlinks: ponto, vírgula, interrogação NÃO fazem parte do link.

### Hífen
# Ref: https://zeroheight.com/33af959d2/v/latest/p/09b368-simbolos-sinais-e-pontuacoes
- Com hífen: bem-vindo(a), boas-vindas, conta-corrente, conta-poupança, conta-salário, ponto-final, Wi-Fi.
- Sem hífen: email, online, offline, conta conjunta.

## REGRAS (lint)

- id: no_click_here
  severity: error
  pattern: /\b(clique\s*aqui|click\s*here)\b/i
  message: "Evite 'clique aqui'. Use uma ação contextual."
  ref: https://zeroheight.com/33af959d2/v/latest/p/04b4f1-botoes-e-links
  suggestions:
    - "Ver detalhes"
    - "Saiba mais"

- id: no_double_space
  severity: info
  pattern: / {2,}/
  message: "Há espaços duplicados. Normalize espaços."
  fix: normalize_spaces

- id: no_space_before_punct
  severity: info
  pattern: /\s+([,.;:!?])/g
  message: "Remova espaço antes de pontuação."
  ref: https://zeroheight.com/33af959d2/v/latest/p/09b368-simbolos-sinais-e-pontuacoes
  fix: remove_space_before_punct

- id: avoid_ellipsis_many
  severity: warn
  pattern: /\.{4,}|…{2,}/
  message: "Evite reticências excessivas. Prefira mensagem objetiva."
  ref: https://zeroheight.com/33af959d2/v/latest/p/09b368-simbolos-sinais-e-pontuacoes

- id: avoid_etc_reticencias
  severity: warn
  pattern: /etc\.\.\./i
  message: "Não use reticências após 'etc.'. Use apenas 'etc.'"
  ref: https://zeroheight.com/33af959d2/v/latest/p/09b368-simbolos-sinais-e-pontuacoes
  suggestions:
    - "etc."

- id: avoid_empty_error_generic
  severity: error
  pattern: /\b(erro\s*inesperado|algo\s*deu\s*errado|ocorreu\s*um\s*erro)\b/i
  message: "Erro genérico. Diga o que aconteceu e o que fazer agora."
  ref: https://zeroheight.com/33af959d2/v/latest/p/1810b5-feedback-de-erro-em-campos-de-dados
  suggestions:
    - "Não foi possível concluir {ação}. Tente de novo."
    - "[Dado] inválido/inválida. Verifique e tente de novo."

- id: avoid_we_are_processing
  severity: info
  pattern: /\b(estamos\s*processando|estamos\s*carregando)\b/i
  message: "Evite sujeito desnecessário. Prefira mensagem curta."
  suggestions:
    - "Processando"
    - "Carregando"

- id: avoid_login_logar
  severity: warn
  pattern: /\b(logar|logado|logada|login|logon)\b/i
  message: "Use 'acessar' e 'acesso' conforme glossário Bradesco."
  ref: https://zeroheight.com/33af959d2/v/latest/p/35b1fa-acesso-a-conta
  suggestions:
    - "Acessar"
    - "Acesso"

- id: avoid_field_required_shouting
  severity: warn
  pattern: /\b(campo\s*obrigatório|required)\b/i
  message: "Prefira orientação específica: 'Informe {campo} pra continuar'."
  ref: https://zeroheight.com/33af959d2/v/latest/p/1810b5-feedback-de-erro-em-campos-de-dados
  suggestions:
    - "Informe o/a {campo}"

- id: avoid_redundant_label_in_helper
  severity: info
  pattern: /\b(digite\s+o\s+seu|insira\s+o\s+sua)\b/i
  message: "Helper não precisa repetir 'digite o seu'. Vá direto ao formato esperado."
  ref: https://zeroheight.com/33af959d2/v/latest/p/72100a-campos-de-dados
  suggestions:
    - "Ex.: {formato}"

- id: punctuation_end_in_labels
  severity: info
  pattern: /:\s*$|[.]\s*$/
  message: "Em labels, não finalize com ponto ou dois-pontos."
  ref: https://zeroheight.com/33af959d2/v/latest/p/09b368-simbolos-sinais-e-pontuacoes
  fix: remove_final_punctuation

- id: avoid_excess_question_marks
  severity: warn
  pattern: /\?{2,}/
  message: "Evite múltiplas interrogações. Mantenha tom calmo."
  ref: https://zeroheight.com/33af959d2/v/latest/p/09b368-simbolos-sinais-e-pontuacoes
  fix: reduce_question_marks

- id: consistent_currency_brl
  severity: info
  pattern: /R\$\d/
  message: "Use espaço após 'R$'. Padrão: 'R$ 1.234,56'."
  ref: https://zeroheight.com/33af959d2/v/latest/p/46f946-moedas
  suggestions:
    - "R$ {valor}"

- id: avoid_date_ambiguous
  severity: info
  pattern: /\b(ontem|ano\s*passado|este\s*mês|este\s*ano|no\s*último\s*mês)\b/i
  message: "Evite datas relativas em mensagens permanentes. Use data explícita."
  ref: https://zeroheight.com/33af959d2/v/latest/p/1447a0-datas-dias-e-horarios
  suggestions:
    - "Use data específica: DD/MM/AAAA."

- id: avoid_horario_with_colon
  severity: info
  pattern: /\b\d{1,2}:\d{2}\b/
  message: "Horários devem usar 'h' em vez de ':'. Ex.: '19h' e não '19:00'."
  ref: https://zeroheight.com/33af959d2/v/latest/p/1447a0-datas-dias-e-horarios
  suggestions:
    - "Use formato: 19h, 8h35"

- id: avoid_etapa_instead_passo
  severity: warn
  pattern: /\betapa\s+\d+\s+de\s+\d+\b/i
  message: "Use 'Passo [número] de [número]' em vez de 'Etapa'."
  ref: https://zeroheight.com/33af959d2/v/latest/p/83f8bb-progressao-de-etapas
  suggestions:
    - "Passo {n} de {total}"

- id: avoid_editar_for_alterar
  severity: warn
  pattern: /\b(editar|edite)\b/i
  message: "Em contexts Bradesco, prefira 'Alterar' em vez de 'Editar'."
  ref: https://zeroheight.com/33af959d2/v/latest/p/04b4f1-botoes-e-links
  suggestions:
    - "Alterar"

- id: avoid_encerrar_sessao
  severity: info
  pattern: /\b(sair\s+da\s+conta|sair\s+do\s+app|encerrar\s+sessão|fechar\s+app)\b/i
  message: "Para sair da conta, use apenas 'Sair'."
  ref: https://zeroheight.com/33af959d2/v/latest/p/04b4f1-botoes-e-links
  suggestions:
    - "Sair"

- id: avoid_voltar_home
  severity: info
  pattern: /\b(voltar\s+para\s+a\s+home|ir\s+para\s+a\s+home|voltar\s+para\s+a\s+tela\s+de\s+início)\b/i
  message: "Use 'Voltar ao início' para retorno à home."
  ref: https://zeroheight.com/33af959d2/v/latest/p/04b4f1-botoes-e-links
  suggestions:
    - "Voltar ao início"

- id: avoid_tem_certeza
  severity: warn
  pattern: /\b(tem\s+certeza|deseja\s+realmente)\b/i
  message: "Use 'Quer [ação]?' ou 'Quer mesmo [ação]?' conforme a severidade."
  ref: https://zeroheight.com/33af959d2/v/latest/p/994dd6-confirmacao-de-exclusao-ou-recusa
  suggestions:
    - "Quer [ação]?"
    - "Quer mesmo [ação]?"

- id: checkbox_sem_eu
  severity: warn
  pattern: /^Eu\s+(li\s+e\s+concordo|concordo)/i
  message: "Em checkbox de aceite, não inicie com 'Eu'. Use 'Li e concordo' ou 'Concordo'."
  ref: https://zeroheight.com/33af959d2/v/latest/p/38c240-aceites-e-preferencias
  suggestions:
    - "Li e concordo"
    - "Concordo"

- id: vezes_nao_x
  severity: info
  pattern: /\d+x\s+de\s+R\$/i
  message: "Prefira 'vezes' por extenso em vez de 'x' (exceto em espaço muito reduzido)."
  ref: https://zeroheight.com/33af959d2/v/latest/p/09b368-simbolos-sinais-e-pontuacoes
  suggestions:
    - "{n} vezes de R$ {valor}"

- id: telefone_sem_hifen
  severity: info
  pattern: /\b\d{4}-\d{4}\b/
  message: "Números de telefone devem usar espaço entre blocos, não hífen."
  ref: https://zeroheight.com/33af959d2/v/latest/p/389182-numeros-e-cifras
  suggestions:
    - "1234 5678"

- id: telefone_sem_parenteses_ddd
  severity: info
  pattern: /\(\d{2}\)/
  message: "Não use parênteses no DDD. Ex.: '11 1234 5678'."
  ref: https://zeroheight.com/33af959d2/v/latest/p/389182-numeros-e-cifras
