# Registro de Provas em Hash

Sistema de preservação de prova digital por impressão criptográfica (SHA-256),
com termo, assinatura ICP-Brasil e registro público de integridade.

**Responsável:** Filipe Ferreira Santana — advogado, OAB/ES 37.159.

---

## Para o magistrado e a parte contrária

A petição indicará um **código de verificação**, no formato `P6N3F-G04X4-1B9KT-P1NRC`.

Com ele, confira a integridade dos arquivos em menos de um minuto:

1. Abra a **[ferramenta de verificação](https://drfilipeferreirasantana.github.io/registro-provas-hash/)**
2. Vá à aba **"Verificar prova"**
3. Escolha o arquivo dos autos e cole o resumo criptográfico constante do termo

O arquivo é lido no próprio aparelho e **não é enviado a servidor algum**.

Os registros ficam em **[`registro/`](registro/)**, onde também há as instruções
completas de verificação, inclusive por linha de comando.

---

## O que este repositório contém, e o que nunca conterá

**Contém:** resumos criptográficos (hashes), datas e a inscrição do responsável.

**Nunca conterá:** nome de pessoa, CPF, número de processo, nome de arquivo, nem
o conteúdo das provas.

O hash é número do qual **não se reconstrói o conteúdo**. Publicado, dá data
certa e demonstra integridade; publicado, nada revela. É o que concilia a
verificabilidade pública com o **sigilo profissional** (Lei 8.906/94 e Código de
Ética e Disciplina da OAB) e com a **LGPD** (Lei 13.709/2018).

Até o nome do arquivo fica de fora, porque nome de arquivo costuma revelar o
teor do que deveria permanecer reservado.

---

## Natureza jurídica — declarada sem reservas

Os termos aqui registrados são **instrumentos particulares**. **Não possuem fé
pública** e **não substituem a ata notarial** de que trata o art. 384 do Código
de Processo Civil, privativa de tabelião.

O que se oferece é a camada de **integridade e data certa**, verificável por
qualquer pessoa de modo independente, somada à **presunção de veracidade quanto
ao signatário** que decorre da assinatura com certificado ICP-Brasil
(MP 2.200-2/2001, art. 10, § 1º) `[CONFERIR REDAÇÃO VIGENTE]`.

Onde a prova digital for o cerne da causa, ou houver risco de perecimento do
conteúdo, a **ata notarial permanece o instrumento adequado**.

---

## A cadeia de integridade

```
  assinatura ICP-Brasil
        |  recai sobre
        v
  termo de preservação (PDF assinado)
        |  contém em seu corpo
        v
  hashes dos arquivos de prova
        |  cada um corresponde a
        v
  arquivos originais, não alterados
```

Uma única assinatura protege o conjunto inteiro: alterar qualquer arquivo de
prova quebra o hash dele, que está dentro do documento assinado.

---

## Ordem das operações — não pode ser invertida

1. Calcular os hashes dos arquivos **originais** (nunca assinados, nunca editados)
2. Gerar o termo, que já contém esses hashes
3. **Assinar o termo** com certificado ICP-Brasil
4. Validar a assinatura
5. Calcular o hash do termo **já assinado** — é ele que fecha a cadeia
6. Publicar o registro

A assinatura grava dados dentro do arquivo, de modo que o PDF assinado é um
arquivo diferente, com hash diferente. Publicar o hash antes de assinar
produziria registro que não confere com o documento juntado aos autos.

---

## Amparo jurisprudencial

**STJ, _Jurisprudência em Teses_, Edição n. 281** — "Direito Penal e Processual Penal em
Ambiente Digital III", de 29/05/2026 (atualizada em 15/05/2026):

> **Tese 3.** "Para a integridade e auditabilidade da prova digital, é necessária a
> preservação da cadeia de custódia e a possibilidade de exame técnico independente, o
> que pode incluir utilização de certificadores específicos como o **algoritmo hash**, em
> observância ao **princípio da mesmidade**."

> **Tese 4.** "Se houver dúvida razoável sobre a integridade e autenticidade da prova
> digital, é necessária a realização de exame pericial para assegurar a confiabilidade do
> material e o exercício do contraditório."

As duas se combinam assim: o hash não dispensa a perícia por decreto — ele **impede que a
dúvida razoável se instale**, por oferecer verificação imediata e independente a qualquer
das partes e ao Juízo.

**Advertência quanto ao alcance:** a Edição n. 281 é de matéria **criminal**. Em causa
cível ou trabalhista, suas teses valem como argumento persuasivo sobre o padrão técnico —
não como precedente diretamente aplicável. A ferramenta explicita essa distinção na aba
"Valor em juízo", e o modelo de petição que ela fornece a declara de modo expresso.

_O periódico consigna não ser repositório oficial de jurisprudência. Confira cada julgado
na base do tribunal antes de protocolar._

---

## Privacidade da ferramenta

Roda inteiramente no navegador. Nenhum arquivo é transmitido. Funciona offline —
e convém usá-la assim com prova sensível.
