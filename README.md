# Projeto Node.js com CI/CD no Azure DevOps ☁️
Projeto exemplo de aplicação Node.js que demonstra a criação de artifacts, pacotes e a configuração de uma pipeline `yml` de CI/CD usando a plataforma Azure DevOps. 

## Estrutura do Projeto 🏗️🧱
- **node_modules:** Diretório que contém as dependências do projeto.
- **.gitignore:** Arquivo que especifica quais diretórios e arquivos devem ser ignorados pelo Git.
- **.npmrc:** Arquivo de configuração do npm que conecta com meu Azure DevOps.
- **package-lock.json:** Arquivo de lock do npm que garante a instalação das mesmas versões de dependências.
- **package.json:** Arquivo de configuração do npm que possui as dependências e scripts do projeto.
- **serves.js:** Arquivo principal do servidor Node.js.


## Artifacts 🚀
Artifacts são arquivos ou pacotes gerados durante o processo de build que são usados em etapas antes do deploy. Eles são uma parte crucial do pipeline de CI/CD, pois permitem a transferência segura e eficiente de builds entre diferentes ambientes (desenvolvimento, teste, produção). **Permitem que os desenvolvedores publiquem e consumam vários tipos de pacotes.**

### Por que os Artifacts são importantes?
- **Consistência:** Garante que o mesmo build é usado em todos os ambientes, reduzindo a chance de problemas específicos de ambiente.
- **Isolamento:** Separa o processo de build do processo de deploy, permitindo que cada etapa seja executada independentemente.
- **Rastreamento:** Facilita o ratreamento e auditoria dos builds, pois cada artefatopode ser versionado e identificado de forma única.

## Pipeline de CI/CD no Azure DevOps 📥
Uma pipeline de CI/CD (Integração Contínua/Entrega Contínua) automatiza o processo de build, teste e deploy de uma aplicação, garantido que as mudanças no código sejam integradas de forma contínua e entregues rapidamente aos ambientes de produção.

### Benefícios do Pipeline CI/CD
- **Automação**: automatiza tarefas repetitivas e sujeitas a erros, como testes e deploys.
- **Qualidade**: garante que todos os commits sejam testados e validados, melhorando a qualidade do código.
- **Velocidade**: acelera o processo de entrega de software, permitindo releases mais rápidos e frequentes.
- **Colaboração**: facilita a colaboração entre devs, integrando mudanças de forma contínua e reduzindo conflitos de merge.

### Estrutura do Pipeline 🏗️

O arquivo `azure-pipelines.yml` define as etapas do pipeline.
1. Trigger: Define que o pipeline será executado para mudanças na branch main.
2. Pool: Especifica a imagem da VM a ser usada para executar o pipeline (ubuntu-latest).
3. Install Node.js: Utiliza a task NodeTool para instalar a versão 20.x do Node.js.
4. Checking Versions: Executa um script Bash para verificar as versões do Node.js e do npm instaladas.
5. Install npm: Reinstala a versão especificada do npm (versão 20.x).