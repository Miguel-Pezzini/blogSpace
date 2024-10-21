<template>
  <Header/>
  <div style="height: 100%; background-color: #141414; display: flex; justify-content: center;">
    <v-icon icon="mdi-reload" class="icon" @click="fetchData"></v-icon>
    <div style="width: 1000px; display: flex; justify-content: center; margin-top: 15px;">
    <ul class="container">
        <cards-posts
        v-for="item in fetchedData"
        :title="item.title"
        :description="item.description"
        :content="item.content"
        :image_url="item.image_url"
        :key="item.source_id"
        :source_url="item.source_url"
        :pubDate="item.pubDate"
        />
      </ul>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import Header from '@/components/HeaderPage.vue';

const fetchedData = ref([]);

// Função para buscar dados da URL
const fetchData = async () => {
  try {
    const response = await fetch('https://newsdata.io/api/1/news?apikey=pub_5535218513ce12419732e56b1804d4858c493&country=br&category=science&size=9'); // Altere para sua URL
    if (!response.ok) {
      throw new Error('Erro na rede: ' + response.statusText);
    }
    const data = await response.json();
    fetchedData.value = data.results; // Atribui os dados recebidos à variável reativa
    console.log(data.results)
  } catch (error) {
    console.error('Erro ao buscar dados:', error);
  }
};
// Chama a função fetchData quando o componente é montado
onMounted(fetchData);
</script>

<style scoped>
  .container {
    display: grid; /* Ativa o layout de grid */
    grid-template-columns: repeat(3, 1fr); /* 3 colunas de largura igual */
    gap: 20px; /* Espaço entre os itens */
    padding: 20px; /* Preenchimento ao redor do container */
  }
  .icon {
    color: #FFF;
    margin-right: 15px;
  }
  .icon:hover {
    cursor: pointer;
    color: #eee;
    border-radius: 2px;
    transition: .2s;
    scale: 1.05;
  }
</style>
