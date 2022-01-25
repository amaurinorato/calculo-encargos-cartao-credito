# calculo-encargos-cartao-credito
Repósitório contendo página para calcular os juros, multa, mora e iof do atraso de uma fatura de cartão de crédito.

O uso é muito simples, basta abrir a página em qualquer navegador e preencher os campos, de acordo com as instruções.

Segue um breve descritivo de cada campo e fórmulas utilizadas:

* **Valor Fatura**: Valor total da fatura que o cliente atrasou
* **Dias atraso até o pagamento**: Quantos dias, a partir do vencimento da fatura, o cliente levou até efetuar o pagamento
* **Valor Encargos Rotativo Ao Mês**: Qual a taxa de rotativo que o emissor do cartão do cliente cobra por atraso
* **Valor Mora Ao Mês**: Qual o valor da mora que o emissor do cartão do cliente cobra por atraso. Geralmente é 1% ao mẽs
* **Valor Multa**: Qual o valor da multa que o emissor do cartão do cliente cobra por atraso. Geralmente é 2% fixo.
* **Valor IOF Fixo**: Imposto definido pelo governo, cobrado sobre operações financeiras, apenas uma vez. Geralmente é fixo e tem o valor de 0,38%
* **Valor IOF Ao Dia**: Imposto definido pelo governo, cobrado sobre operações financeiras, por dia de atraso. Geralmente tem o valor de 0,0082%

## Fórmulas
* **Encargos Rotativo Ao Mês**: `taxaEncargosrotativo / 100 / 30 * diasAtraso * valorFatura`
* **Mora**: `taxaMora / diasMes / 100 * diasAtraso * valorFatura`
* **Multa**: `taxaMulta / 100 * valorFatura`
* **IOF Fixo**: `taxaIofFixo / 100 * valorFatura`
* **IOF diário**: `taxaIofDiario / 100 * diasAtraso * valorFatura`

## Resultados
* **Total Encargos**: soma de todos os encargos que o cliente pagará por ter atrasado. Geralmente esse valor é cobrado na próxima fatura
* **Total Encargos por dia**: valor que o cliente pagará por dia de atraso, desconsiderando as despesas fixas(multa e IOF fixo).
* **Total Encargos Fixos**: valor das despesas fixas(IOF Fixo + Multa) que o cliente pagar, caso atrase a fatura. Não importando a quantidade de dias.
* **Total a ser pago**: Valor total que o cliente pagará, considerando a fatura em atraso + todos os encargos 
