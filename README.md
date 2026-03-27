# 🚀 Deploy Escalável na AWS com CI/CD e IA (Projeto BIA)

Este repositório contém o código-fonte da aplicação BIA, juntamente com toda a infraestrutura e configuração de deploy automatizado desenvolvidos durante a **Imersão AWS e IA**. O foco principal deste projeto é a construção de um ambiente de nuvem altamente disponível, seguro e integrado com Inteligência Artificial para validação de arquitetura.

## 🎯 Objetivo do Projeto
Migrar uma aplicação completa para a nuvem líder de mercado (AWS), garantindo escalabilidade (ECS), automação de entregas (CodePipeline), segurança de rede (ALB e HTTPS) e utilizando agentes de IA modernos (MCP Server) para auxiliar na gestão do cluster.

---

## 🏗️ Arquitetura Cloud e Containerização

A aplicação foi preparada e conteinerizada utilizando **Docker**, com as imagens armazenadas de forma segura no Amazon ECR e orquestradas pelo Amazon ECS.

* **Serviços AWS Utilizados:** ECS (Fargate), ECR, RDS (PostgreSQL), IAM, Application Load Balancer (ALB).
* **Alta Disponibilidade:** Configuração de Target Groups e monitoramento de *health checks* para garantir que o tráfego só seja roteado para instâncias saudáveis.

![Target Group Health](./tg-com-tasks_health.png)
> *Visão do Target Group mostrando as tasks do ECS saudáveis (Healthy) e prontas para receber tráfego.*

---

## ⚙️ Automação com Pipeline CI/CD

Para garantir a integração e entrega contínuas, foi construída uma esteira automatizada na AWS. Qualquer alteração feita no código-fonte no GitHub dispara automaticamente o processo de build e deploy.

* **Fluxo:** Source (GitHub) ➡️ Build (CodeBuild) ➡️ Deploy (ECS).

![Pipeline CI/CD AWS](./pipeline.png)
> *Pipeline completo e executado com sucesso (Source, Build e Deploy).*

---

## 🔒 Segurança e Domínio (HTTPS)

O ambiente foi configurado seguindo as melhores práticas de segurança de rede, expondo a aplicação através de um Application Load Balancer e criptografando o tráfego ponta a ponta.

* Criação de infraestrutura usando linguagem natural no ECS.
* Configuração de domínio personalizado com certificado SSL/TLS (HTTPS).

![Aplicação BIA com HTTPS](./BIA-rodando-com-https.png)
> *Aplicação em produção, rodando com segurança HTTPS.*

---

## 🤖 O Diferencial: Kiro-cli e MCP Server

A estruturação dessa infraestrutura contou com o suporte ativo de Inteligência Artificial para acelerar e validar o processo:
* **Automação com Kiro-cli:** Utilização do Kiro-cli como assistente de IA no terminal para gerar o `Dockerfile`, preparar a aplicação e auxiliar na criação de scripts.
* **Integração MCP Server:** Uso de servidores MCP para permitir que a IA interaja em tempo real com o banco de dados PostgreSQL e com o cluster ECS, além de validar se as configurações de segurança (IAM, Redes) seguiam as melhores práticas da AWS.

![Estrutura e Deploy](./image_1b0c15.png)

---

## 🛠️ Como rodar o projeto localmente
Para executar a aplicação localmente para fins de desenvolvimento, certifique-se de ter o Docker instalado e utilize o comando:

`docker-compose up -d`
