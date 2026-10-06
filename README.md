# Skill de conferência de cálculos trabalhistas

Skill para o Claude que audita provisórias, cálculos de liquidação e relatórios exportados do PJe-Calc, usando o título executivo (sentença, acórdão e decisões posteriores) como referência única.

> Os dados, IDs, nomes e configurações deste repositório são fictícios ou foram sanitizados. Nenhum dado real de clientes ou processos está incluído.

## Objetivo

Reduzir erro humano na conferência de cálculos trabalhistas: o assistente extrai os parâmetros dos documentos, refaz amostras das rubricas materiais e apresenta divergências com critério usado, critério correto, impacto e fundamento, sem inventar verbas, índices ou valores.

## Tecnologias

- Formato de skill do Claude (`SKILL.md` com instruções em Markdown e arquivos de referência carregados sob demanda).
- Não há código executável, dependências ou integrações obrigatórias.

## Como funciona

A skill escolhe um de três modos conforme a finalidade pedida e carrega só a referência correspondente:

| Modo | Arquivo | Uso |
|---|---|---|
| Provisória | `references/provisoria.md` | Estimativa de passivo e conferência de provisória interna |
| Cálculos e impugnação | `references/calculos-e-impugnacao.md` | Elaboração, conta da parte contrária, impugnação, resposta à impugnação e conferência de cálculo de perito ou homologado |
| PJe-Calc | `references/pjecalc.md` | Ficha de parametrização e auditoria de relatório exportado |

Princípios aplicados em todos os modos:

- o título executivo prevalece sobre qualquer prática usual de cálculo;
- cada parâmetro é classificado como confirmado, não localizado ou dependente de validação jurídica;
- dado ausente nunca é preenchido por suposição;
- o fato de o total fechar não é tratado como prova de que a conta está correta;
- duplicidade, reflexo indevido e verba omitida são verificados;
- a saída segue uma tabela padrão de divergências, seguida de resumo por tema (FGTS, encargos, juros e correção);
- a peça só é redigida depois da auditoria concluída.

## Estrutura

```
SKILL.md
references/
  provisoria.md
  calculos-e-impugnacao.md
  pjecalc.md
```

## Como usar

Instale a pasta como skill no Claude, anexe os cálculos e as decisões do processo e descreva a finalidade (por exemplo, conferir um relatório do PJe-Calc contra a sentença).

## Integrações opcionais

O preenchimento direto do PJe-Calc pela tela só ocorre se o recurso de uso do computador estiver disponível, com pedido expresso e supervisão do usuário. Sem isso, a skill apenas prepara parâmetros e confere relatórios exportados.

## Limitações

- O resultado não substitui a revisão do contador ou advogado responsável.
- Afirmações sobre legislação, índices e tabelas atuais dependem de fonte atualizada.
- Documentos digitalizados ilegíveis ou muito extensos podem exigir extração de texto prévia.

## Direitos autorais

Copyright © 2026 Samuel Rodrigues. Todos os direitos reservados.

O código e a documentação deste repositório são protegidos pela Lei nº 9.610/1998 (direitos autorais) e pela Lei nº 9.609/1998 (programa de computador). O uso, a cópia, a modificação ou a distribuição sem autorização prévia e por escrito do autor poderá ser objeto de notificação extrajudicial, de pedido de remoção junto ao GitHub (DMCA) e das medidas judiciais cabíveis.

Para pedir autorização, entre em contato pelo perfil do autor no GitHub.

## Uso

Este repositório é disponibilizado como portfólio e demonstração técnica.

Não é concedida permissão para copiar, modificar, distribuir ou reutilizar este código sem autorização do autor.
