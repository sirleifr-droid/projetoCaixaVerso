# Desafio DevSecOps — Gerenciador de Tarefas

## Sobre o Projeto1
Este repositório faz parte do desafio prático do módulo de DevSecOps da ADA Tech.
Você receberá este projeto com vulnerabilidades propositais e uma pipeline incompleta.
Seu objetivo é **implementar a pipeline de segurança** e **corrigir as vulnerabilidades**.

## Estado atual
A pipeline está **incompleta**. Os steps de segurança precisam ser implementados por você.

## Sua missão
1. Implementar os steps de segurança no `pipeline.yml`
2. Fazer a pipeline **quebrar** ao detectar os problemas
3. Corrigir as vulnerabilidades encontradas
4. Fazer a pipeline **passar** com tudo verde ✅
5. Documentar o funcionamento da pipeline neste README

## O que implementar
- [ ] Secrets Scanning com **Gitleaks**
- [ ] SAST com **Semgrep**
- [ ] SCA com **Grype**
- [ ] Assinatura do artefato com cosign
- [ ] Deploy com **GitHub Pages**

## Como a pipeline funciona  

•	Secrets Scanning (Gitleaks)  
  -	O que faz: Varre o histórico do repositório e os arquivos modificados em busca de credenciais vazadas, chaves de API, senhas e tokens de acesso expostos acidentalmente.  
  -	Importância: Impede que informações sensíveis (como tokens de serviços em nuvem ou chaves privadas) sejam publicadas no controle de versão e comprometam a infraestrutura.  
  -	O Semgrep parou a execução porque detectou uma vulnerabilidade estática no código-fonte da aplicação (como uma falha do tipo XSS ou padrão inseguro).  O uso da função perigosa eval() no arquivo src/script.js na linha 29. O relatório aponta que o eval() pode causar uma vulnerabilidade de injeção de código se receber dados dinâmicos de fontes externas.  


•	SAST - Static Application Security Testing (Semgrep)  
  -	O que faz: Realiza uma análise estática do código-fonte procurando por padrões de código inseguros, vulnerabilidades conhecidas (como OWASP Top 10) e mais práticas de programação.  
  -	Importância: Permite identificar e corrigir falhas de segurança diretamente na base de código antes que a aplicação seja compilada ou executada. > *Problema encontrado:( break the build)  
  -	O Semgrep parou a execução porque detectou uma vulnerabilidade estática no código-fonte da aplicação (como uma falha do tipo XSS ou padrão inseguro).  O uso da função perigosa eval() no arquivo src/script.js na linha 29. O relatório aponta que o eval() pode causar uma vulnerabilidade de injeção de código se receber dados dinâmicos de fontes externas  

•	SCA - Software Composition Analysis (Grype)
  - O que faz: Analisa as dependências e bibliotecas de terceiros utilizadas no projeto para identificar vulnerabilidades conhecidas (CVEs) em pacotes externos.  
  -	Importância: Garante que componentes de código aberto ou bibliotecas de terceiros utilizados no projeto não introduzam brechas de segurança conhecidas.  
  -	O Grype encontrou várias vulnerabilidades conhecidas (CVEs) nas dependências antigas do projeto (como `lodash`, `axios`, `express`, etc.) declaradas no arquivo `package.json`, exigindo a limpeza/atualização das dependências.  


## URL de Produção
> https://sirleifr-droid.github.io/projetoCaixaVerso/
