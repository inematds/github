# Curso Rápido de GitHub

## Módulo 1: Fundamentos do Git e GitHub

### 1.1 O que é Git e GitHub?
- **Git**: Sistema de controle de versão distribuído
- **GitHub**: Plataforma de hospedagem de código usando Git
- **Diferença**: Git é a ferramenta, GitHub é o serviço online

### 1.2 Instalação
1. Baixe o Git: https://git-scm.com/downloads
2. Instale seguindo o assistente
3. Verifique: `git --version`

### 1.3 Configuração Inicial
```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"
```

---

## Módulo 2: Comandos Básicos

### 2.1 Criar um Repositório
```bash
# Criar nova pasta
mkdir meu-projeto
cd meu-projeto

# Inicializar Git
git init
```

### 2.2 Ciclo Básico de Trabalho
```bash
# 1. Verificar status
git status

# 2. Adicionar arquivos
git add .                 # Adiciona todos
git add arquivo.txt       # Adiciona específico

# 3. Fazer commit
git commit -m "Mensagem descritiva"

# 4. Ver histórico
git log
git log --oneline        # Versão resumida
```

### 2.3 Trabalhando com Branches
```bash
# Criar branch
git branch nova-feature

# Mudar de branch
git checkout nova-feature
# OU (comando moderno)
git switch nova-feature

# Criar e mudar ao mesmo tempo
git checkout -b outra-feature

# Listar branches
git branch

# Deletar branch
git branch -d nome-branch
```

---

## Módulo 3: GitHub na Prática

### 3.1 Criar Conta no GitHub
1. Acesse https://github.com
2. Clique em "Sign up"
3. Siga o processo de registro
4. Verifique seu email

### 3.2 Conectar Repositório Local ao GitHub

**Opção 1: Criar repositório no GitHub primeiro**
```bash
# No site GitHub: New Repository
# Copie a URL do repositório criado

# No seu terminal:
git remote add origin https://github.com/seu-usuario/seu-repo.git
git branch -M main
git push -u origin main
```

**Opção 2: Criar do zero localmente**
```bash
# Após criar repositório no GitHub
git remote add origin URL-DO-SEU-REPO
git push -u origin main
```

### 3.3 Comandos para Sincronizar

```bash
# Enviar alterações
git push

# Baixar alterações
git pull

# Clonar repositório existente
git clone https://github.com/usuario/repositorio.git
```

---

## Módulo 4: Colaboração

### 4.1 Fork e Pull Request

**Fork**: Copiar repositório de outra pessoa para sua conta
1. Acesse o repositório desejado
2. Clique em "Fork" (canto superior direito)
3. Clone seu fork: `git clone URL-DO-SEU-FORK`

**Pull Request**: Propor mudanças
1. Faça alterações no seu fork
2. Push para seu repositório
3. No GitHub, clique "New Pull Request"
4. Descreva suas mudanças
5. Aguarde revisão

### 4.2 Issues
- Relatar bugs
- Sugerir features
- Fazer perguntas
- Organizar tarefas

**Criar Issue:**
1. Aba "Issues" no repositório
2. "New Issue"
3. Título e descrição clara
4. Labels apropriadas

---

## Módulo 5: Comandos Essenciais de Resgate

### 5.1 Desfazer Alterações
```bash
# Desfazer mudanças não commitadas
git checkout -- arquivo.txt

# Desfazer último commit (mantém alterações)
git reset --soft HEAD~1

# Desfazer último commit (descarta alterações)
git reset --hard HEAD~1

# Reverter commit específico
git revert HASH-DO-COMMIT
```

### 5.2 Resolver Conflitos
```bash
# Quando ocorre conflito no merge/pull:
# 1. Git marca os arquivos conflitantes
# 2. Abra os arquivos e procure por:
#    <<<<<<< HEAD
#    seu código
#    =======
#    código conflitante
#    >>>>>>> branch

# 3. Edite manualmente para resolver
# 4. Adicione e commite:
git add .
git commit -m "Resolve conflito"
```

---

## Módulo 6: Boas Práticas

### 6.1 Mensagens de Commit
✅ BOM:
```
feat: adiciona sistema de login
fix: corrige bug no carrinho de compras
docs: atualiza README com instruções
```

❌ RUIM:
```
alterações
fix
atualizações diversas
```

### 6.2 Estrutura de Branches
- `main` ou `master`: código de produção
- `develop`: código de desenvolvimento
- `feature/nome`: novas funcionalidades
- `hotfix/nome`: correções urgentes

### 6.3 Arquivo .gitignore
Ignore arquivos desnecessários:
```
# .gitignore
node_modules/
.env
*.log
.DS_Store
dist/
```

---

## Módulo 7: Atalhos e Dicas

### 7.1 Comandos Úteis
```bash
# Status curto
git status -s

# Ver diferenças
git diff

# Ver branches remotas
git branch -r

# Limpar branches deletadas remotamente
git fetch --prune

# Salvar trabalho temporariamente
git stash
git stash pop    # Recuperar depois
```

### 7.2 Aliases
Crie atalhos:
```bash
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status
```

Agora use: `git st` em vez de `git status`

---

## Módulo 8: Recursos e Próximos Passos

### Recursos Úteis
- **Documentação oficial**: https://docs.github.com
- **Git Cheat Sheet**: https://education.github.com/git-cheat-sheet-education.pdf
- **GitHub Learning Lab**: https://lab.github.com
- **Visualizador Git**: https://git-school.github.io/visualizing-git/

### Próximos Passos
1. ✅ Crie seu primeiro repositório
2. ✅ Faça commits diários
3. ✅ Contribua para projetos open source
4. ✅ Aprenda sobre GitHub Actions (CI/CD)
5. ✅ Explore GitHub Pages (hospedagem gratuita)

---

## Exercício Prático Final

**Desafio: Crie seu portfólio no GitHub**

1. Crie repositório `seu-usuario.github.io`
2. Adicione arquivo `index.html` com seu portfólio
3. Faça commit e push
4. Acesse `https://seu-usuario.github.io`

```html
<!-- index.html básico -->
<!DOCTYPE html>
<html>
<head>
    <title>Meu Portfólio</title>
</head>
<body>
    <h1>Bem-vindo ao meu portfólio!</h1>
    <p>Aprendi Git e GitHub!</p>
</body>
</html>
```

---

## Cheat Sheet Rápido

```bash
# Configuração
git config --global user.name "Nome"
git config --global user.email "email"

# Início
git init                    # Iniciar repo
git clone URL              # Clonar repo

# Básico
git status                 # Ver status
git add .                  # Adicionar tudo
git commit -m "msg"        # Commitar
git push                   # Enviar
git pull                   # Baixar

# Branches
git branch nome            # Criar branch
git checkout nome          # Mudar branch
git merge nome             # Mesclar branch

# Histórico
git log                    # Ver commits
git diff                   # Ver diferenças
```

---

**Parabéns!** Você completou o curso rápido de GitHub. Pratique esses comandos e em pouco tempo estará dominando o Git e GitHub! 🚀
