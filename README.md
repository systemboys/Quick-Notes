# 📒 Quick-Notes
Repositório pessoal de **notas rápidas, comandos e dicas técnicas** para agilizar instalações, configurações e soluções em **Linux** e **Windows**.   A ideia é servir como um **bloco de post-its digital** para consultas rápidas no dia a dia.

- [Linux](#linux "Para Linux")
  - [QuickLinux](#quicklinux "QuickLinux")
- [Windows](#windows "Para Windows")
  - [QuickWindows](#comando-powershell-para-executar-o-quickwindows "QuickWindows")

---

## 🚀 Objetivo
- Centralizar anotações úteis de terminal, scripts e configs.
- Facilitar consultas rápidas em tarefas recorrentes.
- Ser uma referência pessoal para setups e troubleshooting.

---

## Linux

### Comandos rápidos após iniciar uma Distro live

Definir a senha do `root` e criar um usuário com o nome `mUrDoCk`:

```bash
sudo passwd root && sudo adduser murdock && sudo usermod -aG sudo murdock
```

Esse comando encadeia três ações no Linux:

1. **`sudo passwd root`** → Define ou altera a senha do usuário **root**.
2. **`sudo adduser murdock`** → Cria um novo usuário chamado **murdock**.
3. **`sudo usermod -aG sudo murdock`** → Adiciona o usuário **murdock** ao grupo **sudo**, permitindo que ele execute comandos administrativos com `sudo`.

Resumindo em jargão corporativo:
Esse pipeline de comandos **ativa a conta root**, **provisiona um novo usuário** e **eleva suas permissões ao nível administrativo**.

---

### QuickLinux

Instalação do `QuickLinux`, um software utilitário com diversos comandos Linux para instalação de pacotes, atualização do Linux etc:

```bash
bash -c "$(curl -fsSL https://github.com/systemboys/QuickLinux/raw/main/Install.sh)"
```

Esse comando faz o seguinte:

1. **`curl -fsSL https://github.com/systemboys/QuickLinux/raw/main/Install.sh`** → Faz o download do script `Install.sh` hospedado no GitHub.

   * `-f` → falha silenciosamente se o download der erro.
   * `-s` → modo silencioso (não mostra barra de progresso).
   * `-S` → exibe mensagens de erro, se ocorrerem.
   * `-L` → segue redirecionamentos.

2. **`bash -c "$( ... )"`** → Executa imediatamente o conteúdo baixado dentro de um shell Bash.

👉 Em termos corporativos: você está **consumindo e executando em tempo real um script remoto**, sem auditoria prévia. É o equivalente a dar **carte blanche** para código de terceiros rodar na sua máquina com seus privilégios.

---

## Windows

### Comando PowerShell para executar o `QuickWindows`

Instalação do `QuickWindows`, um software utilitário com diversos comandos PowerShell para instalação de softwares para Windows, atualização do Windows etc:

```bash
irm qw.gti1.com.br | iex
```

O que esse comando do PowerShell faz?

1. **`irm qw.gti1.com.br`**

   * `irm` é um alias para **`Invoke-RestMethod`**, que faz uma requisição HTTP/HTTPS.
   * Nesse caso, ele baixa o conteúdo (normalmente um script em PowerShell) diretamente do endereço **`qw.gti1.com.br`**.

2. **`| iex`**

   * O pipe (`|`) pega a saída anterior (o script baixado).
   * `iex` é um alias para **`Invoke-Expression`**, que executa o conteúdo recebido como se fosse código PowerShell.

👉 Em resumo: esse comando **baixa um script hospedado em `qw.gti1.com.br` e o executa imediatamente** na máquina Windows.

---

> Esse conteúdo é de meu (`Marcos Aurélio`) uso particular, mas deixei o repositório como `public` para outras pessas verem!
