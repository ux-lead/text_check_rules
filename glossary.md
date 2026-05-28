# glossary.md
# Glossário robusto (pt-BR) . v1.0
# Estrutura: mapeamentos Preferir -> [Sinônimos a evitar] e lista Evitar.
# O plugin pode usar isso para sugestões e substituições automáticas.

## VOCABULARIO

### Preferir
- "Entrar" -> ["Logar", "Login", "Log in", "Sign in"]
- "Acessar" -> ["Logado", "Logada", "Autenticado", "Autenticada"]
- "Sair" -> ["Deslogar", "Sign out"]
- "Conta" -> ["Usuário", "User"]
- "Pessoa" -> ["Usuário", "Cliente"]  # use conforme contexto
- "Pessoas" -> ["Usuários", "Clientes"]
- "Ver detalhes" -> ["Clique aqui", "Saiba mais aqui", "Mais informações aqui"]
- "Saiba mais" -> ["Clique aqui", "Veja mais aqui"]
- "Configurações" -> ["Settings", "Preferências"]  # se o produto padroniza
- "Continuar" -> ["Prosseguir", "Avançar"]  # escolha um padrão
- "Salvar" -> ["Gravar", "Guardar"]
- "Enviar" -> ["Submeter"]
- "Concluir" -> ["Finalizar"]  # escolha um padrão
- "Tente novamente" -> ["Recarregue a página", "Atualize", "Dê um refresh"]
- "Não foi possível concluir" -> ["Falhou", "Deu ruim", "Não deu certo"]
- "Não foi possível carregar" -> ["Erro ao carregar", "Falha ao carregar"]  # padronize
- "Carregando" -> ["Estamos carregando"]  # prefira curto
- "Processando" -> ["Estamos processando"]  # prefira curto
- "Excluir" -> ["Deletar", "Apagar"]  # escolha um padrão
- "Remover" -> ["Retirar"]  # escolha um padrão
- "Editar" -> ["Alterar"]  # escolha um padrão
- "Verificar" -> ["Checar"]  # escolha um padrão
- "Confirmar" -> ["OK", "Sim"]  # para CTA
- "Cancelar" -> ["Não"]  # para CTA

### Evitar
- "Clique aqui"
- "Ops!"
- "Deu ruim"
- "Falhou"
- "Logar"
- "Logado"
- "Deslogar"
- "Só hoje"
- "Última chance"
- "Erro inesperado"
- "Algo deu errado"

## REGRAS (lint)
- id: glossary_avoid_terms_core
  severity: warn
  pattern: /\b(clique\s*aqui|ops!|deu\s*ruim|falhou|logar|logado|deslogar|só\s*hoje|última\s*chance|erro\s*inesperado|algo\s*deu\s*errado)\b/i
  message: Termo fora do glossário. Substitua por termo preferencial.
  suggestions:
    - "Ver detalhes"
    - "Não foi possível concluir"
    - "Entrar"
    - "Tente novamente"
  fix: replace_from_glossary

- id: glossary_prefer_human_terms
  severity: info
  pattern: /\b(usuário|clientes)\b/i
  message: Considere termos mais humanos quando fizer sentido ao contexto.
  suggestions:
    - "pessoa"
    - "pessoas"

- id: glossary_prefer_specific_cta
  severity: warn
  pattern: /^(ok|sim|não)$/i
  message: Prefira CTA específico (verbo + objeto) em vez de OK/Sim/Não.
  suggestions:
    - "Confirmar"
    - "Cancelar"
    - "Continuar"
