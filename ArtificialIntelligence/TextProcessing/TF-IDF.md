# Term Frequency - Inverse Document Frequency [ TF-IDF ]

> *Domain: Textual data mining/processing*

**Main Idea**

- The words which appear more frequently represents higher significance for some language tasks but, some words( i.e. `stopwords` )  often occur due to syntax requirements than to represent semantics.

- The words occurring less frequently on the other hand, might carry important information to distinguish between semantics and hence should represent higher significance ( i.e. more weight ).

## Term Frequency [ `tf` ]

- The ratio of number of times the word appears in a document ($n_{i,j}$) compared to total number of words in that document $(\sum_k{n_{i,j}})$. 

$$
tf_{i,j} = \frac{n_{i,j}}{\sum_k{n_{i,j}}}
$$

- Where $tf_{i,j}$ is number of occurrences in `i,j`

- **TF** increases with $n_{i,j}$ and each document has it's own `tf`

## Inverse Data Frequency [ `idf` ]

- The weights of common/rare words across all documents in the corpus.

- It is logarithmic scaled inverse fraction of total number of documents  in  the corpus $(N)$ to the number documents that contains the term $(df_t)$

$$
idf(w) = \log{\left(\frac{N}{df_t}\right)}
$$

- Rare words has high `idf` score/ weight.

## TF-IDF

- Combining `tf` and `idf` scores to introduce weight of a word in a document in the corpus.

$$
\boxed{
    w_{i,j} = tf_{i,j} \times \log{\left(\frac{N}{df_i}\right)}
}
$$

- Where, $df_i$ is number of document containing `i`

****


