<script lang="ts">
export default {
    name: 'ConteudoPrincipal',  // Nome do componente Vue
    data() {
        return {
            ingredientes: ['Alho', 'Manteiga', 'Orégano']  // Dados do componente: uma lista de ingredientes
        }
    }
}
</script>


<template>
    <main class="conteudo-principal"> <!-- Elemento principal com a classe 'conteudo-principal' -->
        <section>
            <span class="subtitulo-lg sua-lista-texto">
                Sua lista:
            </span>

            <!-- Lista de ingredientes, mostrada apenas se houver ingredientes (v-if)-->
            <ul v-if="ingredientes.length" class="ingredientes-sua-lista">
                <li v-for="ingrediente in ingredientes" v-bind:key="ingrediente" class="ingrediente">
                    {{ ingrediente }} <!-- Mostra cada ingrediente na lista -->
                </li>
            </ul>

            <!-- Mensagem exibida se a lista de ingredientes estiver vazia (v-else)-->
            <p v-else class="paragrafo lista-vazia">
                <img src="../assets/imagens/icones/lista-vazia.svg" alt="Ícone de pesquisa">
                Sua lista está vazia, selecione ingredientes para iniciar
            </p>
        </section>
    </main>
</template>


<style scoped>
.conteudo-principal {
    padding: 6.5rem 7.5rem;  /* Espaçamento interno (padding) */
    border-radius: 3.75rem 3.75rem 0rem 0rem;  /* Bordas arredondadas */
    background: var(--creme, #FFFAF3);  /* Cor de fundo */
    color: var(--cinza, #444);  /* Cor do texto */

    display: flex;  /* Define como flexbox */
    flex-direction: column;  /* Orienta os itens em coluna */
    align-items: center;  /* Alinha os itens ao centro */
    gap: 5rem;  /* Espaço entre os itens */
}

.sua-lista-texto {
    color: var(--coral, #F0633C);  /* Cor do texto */
    display: block;  /* Exibe como bloco */
    text-align: center;  /* Alinha o texto ao centro */
    margin-bottom: 1.5rem;  /* Margem inferior */
}

.ingredientes-sua-lista {
    display: flex;  /* Define como flexbox */
    justify-content: center;  /* Centraliza os itens */
    gap: 1rem 1.5rem;  /* Espaçamento entre os itens */
    flex-wrap: wrap;  /* Permite que os itens quebrem para a próxima linha */
}

.ingrediente {
    display: inline-block;  /* Exibe como bloco em linha */
    border-radius: 0.5rem;  /* Bordas arredondadas */
    min-width: 4.25rem;  /* Largura mínima */
    padding: 0.5rem;  /* Espaçamento interno (padding) */
    text-align: center;  /* Alinha o texto ao centro */
    transition: 0.2s;  /* Transição suave */
    color: var(--creme, #FFFAF3);  /* Cor do texto */
    background: var(--coral, #F0633C);  /* Cor de fundo */
    font-weight: 700;  /* Peso da fonte */
}

.lista-vazia {
    display: flex;  /* Define como flexbox */
    justify-content: center;  /* Centraliza os itens */
    align-items: center;  /* Alinha os itens ao centro */
    flex-wrap: wrap;  /* Permite que os itens quebrem para a próxima linha */
    gap: 0.25rem;  /* Espaçamento entre os itens */

    color: var(--coral, #F0633C);  /* Cor do texto */
    text-align: center;  /* Alinha o texto ao centro */
}

/* Estilos responsivos para telas menores */
@media only screen and (max-width: 1300px) {
    .conteudo-principal {
        padding: 5rem 3.75rem;  /* Ajusta o espaçamento interno (padding) */
        gap: 3.5rem;  /* Ajusta o espaçamento entre os itens */
    }
}

@media only screen and (max-width: 767px) {
    .conteudo-principal {
        padding: 4rem 1.5rem;  /* Ajusta o espaçamento interno (padding) */
        gap: 4rem;  /* Ajusta o espaçamento entre os itens */
    }
}
</style>