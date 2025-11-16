# Análise de Complexidade Ciclomática e Fluxo de Controle

Este repositório contém a análise de **Complexidade Ciclomática** de um trecho de código Java, juntamente com o diagrama de fluxo de controle correspondente e os caminhos de execução identificados.

## Planilha 
<img width="780" height="551" alt="image" src="https://github.com/user-attachments/assets/3392da68-0cf9-4165-932a-ae966deba92d" />


## 2. Código-Fonte Analisado

O trecho de código Java analisado é responsável pela conexão com o banco de dados e pela verificação de credenciais de usuário.

![Trecho de Código Java Analisado](https://private-us-east-1.manuscdn.com/sessionFile/Vx735Nao2WOJTLlWo6OEtI/sandbox/U3s1tJcMjWc7UbQwTVLwbr-images_1763250850798_na1fn_L2hvbWUvdWJ1bnR1L3Bhc3RlZF9maWxlXzNkRGFucF9pbWFnZQ.png?Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9wcml2YXRlLXVzLWVhc3QtMS5tYW51c2Nkbi5jb20vc2Vzc2lvbkZpbGUvVng3MzVOYW8yV09KVExsV282T0V0SS9zYW5kYm94L1UzczF0SmNNaldjN1ViUXdUVkx3YnItaW1hZ2VzXzE3NjMyNTA4NTA3OThfbmExZm5fTDJodmJXVXZkV0oxYm5SMUwzQmhjM1JsWkY5bWFXeGxYek5rUkdGdWNGOXBiV0ZuWlEucG5nIiwiQ29uZGl0aW9uIjp7IkRhdGVMZXNzVGhhbiI6eyJBV1M6RXBvY2hUaW1lIjoxNzk4NzYxNjAwfX19XX0_&Key-Pair-Id=K2HSFNDJXOU9YS&Signature=jbugl541hqwFR5Qb~VB8bxPZVMTfEnEsbs9tJiXXfHTJI21gM0gujp6wOrmgiBy5hwWFOnhjxncozBdL2Pt-D~-rr9ah8cutsaKEPiBEhWkL-KX05RkotfTZawAh1HjMM8iXsxSxwc4DVDiPrNDn1v97gFR-WeezYGYoNUcMulsOXJebxCCdfg81TJJYO~pAWsOCD7VElkdZ-K8Lvl6V4F-VuVoHtNDR4ln7a8qrzjSBrzEp9lxNFRXG5DMD~yPEquJ8dAORXcuNHRcw9s6RlYtKgKROAP4sxd2dcJXn8aiASJzMhqnKvb4aekQFwuoUG5oQ8VPOpOm9YCsmEwe9-g__)

## 3. Notação de grafo de fluxo
O diagrama a seguir representa o fluxo de controle do método `verificarUsuario`, com os nós numerados de 1 a 10.

![Diagrama de Fluxo de Controle](https://private-us-east-1.manuscdn.com/sessionFile/Vx735Nao2WOJTLlWo6OEtI/sandbox/U3s1tJcMjWc7UbQwTVLwbr-images_1763250850801_na1fn_L2hvbWUvdWJ1bnR1L3Bhc3RlZF9maWxlX2dHNVp1OV9pbWFnZQ.png?Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9wcml2YXRlLXVzLWVhc3QtMS5tYW51c2Nkbi5jb20vc2Vzc2lvbkZpbGUvVng3MzVOYW8yV09KVExsV282T0V0SS9zYW5kYm94L1UzczF0SmNNaldjN1ViUXdUVkx3YnItaW1hZ2VzXzE3NjMyNTA4NTA4MDFfbmExZm5fTDJodmJXVXZkV0oxYm5SMUwzQmhjM1JsWkY5bWFXeGxYMmRITlZwMU9WOXBiV0ZuWlEucG5nIiwiQ29uZGl0aW9uIjp7IkRhdGVMZXNzVGhhbiI6eyJBV1M6RXBvY2hUaW1lIjoxNzk4NzYxNjAwfX19XX0_&Key-Pair-Id=K2HSFNDJXOU9YS&Signature=BusEGKUbAeY1FGUmfatrLDv3SDb2RJ6dt10u2R2Tvy2yBWiXxOoPH7ryLtIVajZhWUMsJKT-5Fo0otr4-5afq--UhWSMMVZO~XO-US~N6vudTmBVvkDyZlh-x738wb96DbDBbV8zkcug0gaTAyOdM8fWo8lKePFr-HI~6oVzQUk~ER-nJB5EFXi4Ypii2~SWhuy4mxeUgaI3KQC4wVomnjkMai5Tb3Snp3aTW75Ibt~OtZOe2nhzS7iqL0zQR~OLoEsirJjgHE5DTQ2LftCMPx6KOpzC1977LS3txFOtuhkWsjC2Qu2XW3L9M2ATmaklrCEeccz9fOSiND4z8efXgg__)

## 4. Análise de Complexidade Ciclomática

A Complexidade Ciclomática $V(G)$ é uma métrica de software que indica o número de caminhos linearmente independentes em um grafo de fluxo de controle. É um indicador da complexidade e testabilidade do código.

### 4.1. Identificação dos Pontos de Decisão (P)

Os pontos de decisão (predicados) no código que aumentam a complexidade são:

| Ponto de Decisão | Localização no Código | Contagem |
| :--- | :--- | :--- |
| `if (rs.next())` | Linha 29 | 1 |
| `catch (Exceção)` | Linha 32 (Bloco `try-catch` para a verificação) | 1 |
| **Laços (for/while)** | Não há laços no trecho analisado | 0 |
| **Total de Pontos de Decisão (P)** | | **2** |

### 4.2. Cálculo da Complexidade Ciclomática

A Complexidade Ciclomática $V(G)$ é calculada pela fórmula:

$$V(G) = P + 1$$

Onde $P$ é o número total de pontos de decisão.

| Variável | Valor |
| :--- | :--- |
| $P$ | 2 |
| $V(G)$ | $2 + 1 = 3$ |

**Resultado:** A Complexidade Ciclomática do método analisado é **3**.

## 5. Caminhos de Execução Identificados

A Complexidade Ciclomática de 3 indica que existem **3 caminhos linearmente independentes** que devem ser testados para garantir a cobertura completa do código.

Os caminhos identificados são:

| Caminho | Descrição | Sequência de Nós |
| :--- | :--- | :--- |
| **Caminho de Login Válido** | Execução bem-sucedida da consulta e credenciais válidas. | `1 – 2 – 3 – 4 – 5 – 6 – 7 – 8 – 9` |
| **Caminho de Login Inválido** | Execução bem-sucedida da consulta, mas credenciais inválidas (usuário não encontrado). | `1 – 2 – 3 – 4 – 5 – 6 – 9` |
| **Caminho de Falha Técnica** | Falha na execução da consulta (exceção no bloco `try-catch`). | `1 – 2 – 3 – 4 - 9` |

***

*Análise gerada por Manus AI.*
