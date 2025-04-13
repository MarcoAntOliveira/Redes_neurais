# Redes_neurais
Este repositorio é dedicado a redes neurais e deep learning
Claro, Marcos! Abaixo está a transcrição em **Markdown**, com as equações de atualização de pesos e a dedução do gradiente, além da fórmula para atualizar o peso  $b_m$.

---

# Redes Neurais

## Função de Erro

A função de custo (erro quadrático médio):

$$E = \sum_{j=1}^M (s_j - y_j)^2$$

-  $y_j$: Saída esperada  
-  $s_j$: Saída obtida

---

## Saída do neurônio

$$s_j = \sigma\left( \sum_m w_{mj} a_m + b_j \right)$$

Onde:

-  $\sigma$: função sigmoide  
-  $a_m$: saída da camada anterior

---

## Atualização dos pesos  $w_{mj}$

Usando gradiente descendente:

$$
w_{mj} \leftarrow w_{mj} - \eta \frac{\partial E}{\partial w_{mj}}$$

Cálculo do gradiente:

$$
\frac{\partial E}{\partial w_{mj}} = 2 \sum (s_j - y_j) \cdot \sigma'\left(\sum_m w_{mj} a_m + b_j \right) \cdot a_m$$

---

## Atualização dos pesos da camada oculta  $w_{km}$

$$
\frac{\partial E}{\partial w_{km}} = 2 \sum_j (s_j - y_j) \cdot \sigma'\left(w_{mj} a_m + b_j \right) \cdot \sigma'\left(\sum_k w_{km} a_k + b_m\right) \cdot a_k$$

---

## Atualização do viés  $b_m$

A derivada da função de custo em relação ao viés  $b_m$ é:

$$
\frac{\partial E}{\partial b_m} = 2 \sum_j (s_j - y_j) \cdot \sigma'\left(w_{mj} a_m + b_j \right) \cdot \sigma'\left(\sum_k w_{km} a_k + b_m \right)$$

Atualização:

$$
b_m \leftarrow b_m - \eta \frac{\partial E}{\partial b_m}$$

---

Claro, Marcos! Aqui está a **transcrição em Markdown** das equações da sua nova imagem — com a dedução da derivada parcial da função de custo  $C$ em relação aos pesos  $w_{pk}$ e ao viés  $b_k$.

---

# Derivadas parciais para retropropagação

## Objetivo:  
Calcular:

$$
\frac{\partial C}{\partial w_{pk}} = ?$$

---

## Expressão intermediária

$$
a_k \cdot \sigma'\left( \sum (w_{pk} \cdot E_p + b_k) \right)$$

### Decomposição em partes (regra da cadeia):

$$
\frac{\partial C}{\partial w_{pk}} = 
\frac{\partial C}{\partial s_j} \cdot 
\frac{\partial s_j}{\partial \sigma} \cdot 
\frac{\partial \sigma}{\partial a_m} \cdot 
\frac{\partial a_m}{\partial \sigma} \cdot 
\frac{\partial \sigma}{\partial a_k} \cdot 
\frac{\partial a_k}{\partial w_{pk}}$$

Com os termos identificados:

-  $\frac{\partial a_k}{\partial w_{pk}} = E_p$
-  $\frac{\partial \sigma}{\partial a_k} = \sigma'(a_k)$
-  $\frac{\partial a_m}{\partial \sigma} = \sum w_{km}$
-  $\frac{\partial \sigma}{\partial a_m} = \sigma'(a_m)$

---

## Derivada do custo em relação ao peso  $w_{pk}$

$$
\frac{\partial C}{\partial w_{pk}} = 
2 \sum (s_j - y_j) \cdot \sigma'\left( \sum w_{mj} a_m + b_j \right) \cdot 
\sum w_{mj} \cdot \sigma'\left( \sum w_{km} a_k + b_m \right) \cdot 
\sum w_{xk} \cdot \sigma'\left( \sum w_{pk} E_p + b_k \right) \cdot E_p$$

---

## Derivada do custo em relação ao viés  $b_k$

$$
\frac{\partial C}{\partial b_k} = 
2 \sum (s_j - y_j) \cdot \sigma'\left( \sum w_{mj} a_m + b_j \right) \cdot 
\sum w_{mj} \cdot \sigma'\left( \sum w_{km} a_k + b_m \right) \cdot 
\sum w_{xk} \cdot \sigma'\left( \sum w_{pk} E_p + b_k \right)$$

---

Se quiser, posso montar isso em LaTeX ou gerar PDF pra facilitar seus estudos ou colocar no relatório do projeto. Quer?
