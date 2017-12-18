![avatar](https://raw.githubusercontent.com/trezoteam/git-style-guide/master/identidade-nova-azul.png)

# Guia de uso do git

## Flow

Todo projeto deve ter no mínimo 2 branches, uma chamada develop e master. 

* A branch **MASTER** é que está publicada em produção, todo código já está aprovado pelo cliente 
* A branch **DEVELOP** é a publicada em homologação e a que usamos para códigos ainda em desenvolvimento 

Para desenvolver, sempre deve ser criada uma brach a partir da MASTER e sempre deve levar o nome hotfix/nºtarefa-descricao ou feature/nºtarefa-descricao 

```
  **hotfix** para correções rápidas
  **feature** para novas funcionalidades
```

Para criar uma branch sempre ir antes na master (git checkout master) e fazer pull (git pull origin master) para receber os códigos atualizados, então criar a branch (git checkout -b hotfix/123-correios) Então os passos a seguir são: 

```
1- git checkout master
2- git pull origin master
3- git checkout -b hotfix/123-correios (seguir a regra de nomeação)
```
Após desenvolver, commitar seus arquivos na própria branch e efetuar o push usando o git push origin nomedabranch 

```
1- git commit -m 'mensagem do commit' arquivos.php
2- git push origin hotfix/123-correios
```

Na hora de mergear na develop e master deve ser requisitado o pull request (feito via Gitlab) e assim a equipe vai avaliar o código e propor melhorias, caso necessário. Após aprovado por duas pessoas você está apto a mergear sua branch na develop ou master, manualmente pelo GitLab. 

## Branches

  - [1.0](#) Escolha nomes curtos e explicativos.
  > Utilize sempre o identificador correspondente (feature para novas implementações ou hotfix para correção de erros) seguido de uma barra (/) contendo o número da tarefa no nosso sistema interno e um traço com um texto que identifique o que será feito (livre).

```
# bom: usando identificadores
$ git checkout -b hotfix/123-erro-login

# ruim: muito vago
$ git checkout -b erro
```

  - [1.1](#) Use traços para seprar palavras.

```
# bom: usando traços
$ git checkout -b feature/321-checkout-transparente

# ruim: muito vago
$ git checkout -b feature/321-checkout_transparente
```

## Commits

  - [2.0](#) Cada commit deve representar uma mudança lógica apenas.
    > Não faça um único commit contendo várias lógicas ou implementaçoes. Por exemplo: corrigiu um bug e otimizou a performance de um código, faça dois commits separados identificando cada coisa.
