# Memory-INSS: Assistente de Análise Previdenciária com Memória Persistente

Este projeto configura um ambiente de desenvolvimento com o **Cline**, um assistente de IA, para atuar como um "Assistente de Análise Previdenciária do INSS". Sua principal característica é o uso de um **Grafo de Conhecimento (Knowledge Graph)** persistente, garantindo que o assistente aprenda e retenha informações específicas do domínio previdenciário a cada interação.

## Funcionalidades Principais

-   **Memória Persistente:** Utiliza um servidor MCP (Model Context Protocol) com a imagem `mcp/memory` do Docker para criar uma base de conhecimento que sobrevive entre sessões. Os dados são armazenados localmente no diretório `memory_inss/`.
-   **Protocolo de Conhecimento:** O assistente segue um rigoroso protocolo (`.clinerules`) para gerenciar o conhecimento: ele verifica a existência de informações antes de criar, pede confirmação para atualizar ou deletar, e cita proativamente a memória como fonte ao responder.
-   **Isolamento de Projetos:** A configuração garante que a memória deste projeto seja totalmente isolada, não interferindo com outros projetos que possam usar a mesma tecnologia.
-   **Especialização em INSS:** O assistente é configurado para entender e utilizar a terminologia, legislação e procedimentos específicos do direito previdenciário brasileiro.

## Exemplo de Uso

A principal vantagem é a capacidade de ensinar regras de negócio e fatos específicos ao assistente. Uma vez ensinado, ele aplicará esse conhecimento em tarefas futuras.

Para salvar uma informação na memória, basta instruir o assistente de forma direta:

> **Você:** Salve na memória: 'Não encaminhar PPP pelo artigo 301 da IN128/22 se for agente frio, eletricidade, radiações ionizantes e umidade, porque é só até 05 de março de 1997. Daí nem envia para a perícia.'

O assistente irá processar, criar as entidades e relações no Grafo de Conhecimento e, em análises futuras de processos que envolvam PPP com esses agentes, ele aplicará essa regra automaticamente.

## Isenção de Responsabilidade

Esta ferramenta é um **assistente de produtividade** e não substitui o julgamento profissional do servidor público.

-   **Responsabilidade do Usuário:** O usuário final é inteiramente responsável por todas as análises, despachos e decisões tomadas. Cada informação gerada pelo assistente deve ser verificada e validada.
-   **Ferramenta de Apoio:** O objetivo deste projeto é auxiliar na organização e recuperação de informações, aumentando a eficiência e a precisão. Ele não possui capacidade de decisão.
-   **Sem Garantias:** O uso desta ferramenta é por conta e risco do usuário. Nenhuma garantia de precisão ou adequação a um propósito específico é fornecida.

## Contato

Para dúvidas, sugestões ou mais informações sobre o projeto, entre em contato:

-   **E-mail:** wanderleyamorim.com@gmail.com
