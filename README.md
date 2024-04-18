
---

# Projeto: Script de Infraestrutura Automatizada

Este projeto consiste na criação de um script que automatiza a configuração inicial de infraestrutura em um servidor Ubuntu. O script cria diretórios, grupos de usuários, usuários e atribui permissões de acordo com as necessidades especificadas.

## Passo a Passo


###  1: Crie o Diretório `/scripts`

Logado como root Abra o terminal e crie o Diretiro `/scripts`. na pasta raiz, Você pode fazer isso usando o comando `mkdir`:

```bash
mkdir /scripts
```

### 2: Criar o Arquivo `iacl.sh`

Use o editor de texto de sua preferência para criar o arquivo `iacl.sh` e adicionar o conteúdo fornecido. Você pode usar o editor `nano`, por exemplo:

```bash
 nano iacl.sh
```

Isso abrirá o editor `nano` com um novo arquivo chamado `iacl.sh`. Cole o conteúdo:

```bash
#!/bin/bash

echo "Criando diretórios..."

mkdir /publico
mkdir /adm
mkdir /ven
mkdir /sec 

echo "Criando grupos de usuários..."

groupadd GRP_ADM
groupadd GRP_VEN
groupadd GRP_SEC

echo "Criando Usuários..."

useradd carlos -m -s /bin/bash $(openssl passwd -crypt senha123) -G GRP_ADM 
useradd maria -m -s /bin/bash $(openssl passwd -crypt senha123) -G GRP_ADM
useradd joao -m -s /bin/bash  $(openssl passwd -crypt senha123) -G GRP_ADM

useradd debora -m -s /bin/bash $(openssl passwd -crypt senha123) -G GRP_VEN
useradd sebastiana -m -s /bin/bash $(openssl passwd -crypt senha123) -G GRP_VEN
useradd roberto -m -s /bin/bash $(openssl passwd -crypt senha123) -G GRP_VEN

useradd josefina -m -s /bin/bash $(openssl passwd -crypt senha123) -G GRP_SEC
useradd amanda -m -s /bin/bash $(openssl passwd -crypt senha123) -G GRP_SEC
useradd rogerio -m -s /bin/bash $(openssl passwd -crypt senha123) -G GRP_SEC

echo "Especificando permissões dos diretórios..."

chown root:GRP_ADM /adm
chown root:GRP_VEN /ven
chown root:GRP_SEC /sec

chmod 770 /adm
chmod 770 /ven
chmod 770 /sec
chmod 777 /publico

echo "Fim....."
```

### 3: Salvar e Sair

Depois de colar o conteúdo, pressione `Ctrl + O` para salvar o arquivo e `Enter`. Em seguida, pressione `Ctrl + X` para sair do editor.

### 4: Tornar o Arquivo Executável

Antes de executar o script, certifique-se de torná-lo executável com o comando:

```bash
 chmod +x iacl.sh
```

Agora o arquivo `iacl.sh` está pronto para ser executado.



### 5: Executar o Script

Após clonar o repositório, navegue até o diretório onde o script está localizado e execute-o. Certifique-se de ter permissões de superusuário para executar o script.

```bash
cd /scripts
 ./iacl.sh
```

### 6: Revisar a Infraestrutura

Após a execução do script, revise a infraestrutura criada para garantir que tudo esteja configurado corretamente. Verifique se os diretórios, grupos de usuários, usuários e permissões foram criados conforme esperado.

### 7: Modificar o Script (Opcional)

Caso necessário, você pode modificar o script para atender às necessidades específicas da sua infraestrutura. Certifique-se de entender o que cada parte do script faz antes de fazer alterações.

## 8: Subir Arquivos para o GitHub

Subir os arquivos requer um Token de acesso.



1.  Clique na sua foto de perfil no canto superior direito e selecione "Settings" (Configurações).

2.  No menu à esquerda, role para baixo até encontrar "Developer settings" (Configurações de desenvolvedor) e clique nele.

3. Na página "Developer settings", clique em "Personal access tokens".

4.  Clique em "Generate new token" (Gerar novo token).

5.  Dê um nome ao token e selecione as permissões necessárias.

6.  Clique em "Generate token" (Gerar token).

7.  Copie o token gerado. Esta será a única vez que você verá o token completo.

8.  Utilize o token gerado como método de autenticação em operações que requerem acesso à sua conta do GitHub.

9. Na linha de comando insira os codigos:

```bash
git add .
git commit -m "Adicionar descrição das alterações"
git branch -M main
git remote add origin "URl do seu Repositório"
"Nome de usuário do GitHub"
"Token de Acesso"
```
 o arquivo [iacl.sh](https://github.com/Lugaus/-Infraestrutura-como-C-digo-Script-de-Criacao-de-Estrutura-de-Usu-rios-Diret-rios-e-Permissoes/blob/main/iacl.sh) Foi upado no Diretório de sua escolha.
 
## Notas Importantes

- Este script foi projetado para automatizar a configuração inicial de infraestrutura em um servidor Ubuntu. Certifique-se de revisar e testar completamente antes de usar em um ambiente de produção.
- Sempre mantenha o controle de versão do script e documente quaisquer alterações significativas.
- Se encontrar problemas ou tiver sugestões de melhorias, sinta-se à vontade para abrir uma issue ou enviar uma solicitação de pull no repositório do GitHub.

---
