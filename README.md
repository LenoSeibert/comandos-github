# Manual do GitHub

> Atenção esse mini manual é para uso no repositório pessoal.
> Para trabalhos em equipe deve se usar alguns comandos a mais.

## 01 - Gerar chave SSH no pelo terminal Debian/Derivados

```bash
sudo ls -al ~/.ssh #Para ver chaves existentes
sudo ssh-keygen -t ed25519 -C "your_email@example.com" #Gera a chave so dar enter nas perguntas
#Mas da onde saiu esse ed25519? EdDSA é o tipo de criptografia
sudo eval "$(ssh-agent -s)" #Inicia o agente ssh, vai mostrar o numero do processo
sudo ssh-add ~/.ssh/id_ed25519 #Adiciona a chave ao ssh-agent Chave Privada
sudo cat  ~/.ssh/id_ed25519.pub #Para ver e copiar a chave publica, 
#que vai no site do GitHub
sudo ssh -T git@github.com #Testa a conexão 
```
### Link da documentação do GitHub 
[Conectar-se ao GitHub com SSH](https://docs.github.com/pt/github/authenticating-to-github/connecting-to-github-with-ssh)

## 02 - Crie seu repositório no seu GitHub

```bash
#Quando não criou o readme pelo site
echo "# Algo..." >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:USER/Repositorio.git
git push -u origin main
```

OU

```bash
#quando ja tem algo no repositorio
git remote add origin git@github.com:USER/Repositorio.git
git branch -M main
git push -u origin main
```

## 03 - Salvando no Stage e fazendo Commit

OBS: Só vai funcionar para atualização de arquivo. O arquivo ja deve ter sido adicionado anteriormente.

```bash
git commit -am "Mensagem" #adiciona a stage area e faz o commit ao mesmo tempo
```

## 04 - Salvando a alteração no GitHub

```bash
git push #Sicroniza o local com a nuvem do github
```

## 05 - Pegar as alterações feitas direto no site do GitHub

```bash
git pull #Puxa as modificação feitas pelo site
```

## 06 - Fazendo um clone

```bash
git clone shh/https #Pode se usar via ssh ou via https
```
