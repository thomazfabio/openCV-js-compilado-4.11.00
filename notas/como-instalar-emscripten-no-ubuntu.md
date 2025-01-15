Para instalar o **Emscripten** no **Ubuntu**, siga os passos abaixo. O Emscripten é uma ferramenta que permite compilar código C/C++ para JavaScript, e é necessária para compilar o **OpenCV.js**.

### Passos para Instalar o Emscripten no Ubuntu

#### 1. **Instalar Dependências**
Antes de instalar o Emscripten, instale as dependências necessárias:

```bash
sudo apt update
sudo apt install -y build-essential cmake python3 git
sudo apt install -y clang
sudo apt install -y nodejs npm
```

#### 2. **Instalar o Emscripten via `emsdk`**

Emscripten fornece um **SDK** chamado `emsdk` para instalar e gerenciar diferentes versões do compilador.

- **Clone o repositório do Emscripten SDK**:

```bash
git clone https://github.com/emscripten-core/emsdk.git
cd emsdk
```

- **Instale a versão mais recente do Emscripten**:

```bash
./emsdk install latest
```

Isso vai baixar e instalar a versão mais recente do Emscripten e também o **LLVM**, necessário para a compilação.

- **Ative o Emscripten**:

```bash
./emsdk activate latest
```

Isso define o ambiente para usar o Emscripten.

#### 3. **Configurar o Ambiente**

Após instalar e ativar o Emscripten, adicione as variáveis de ambiente necessárias ao seu terminal:

```bash
source ./emsdk_env.sh
```

Para garantir que isso seja feito automaticamente toda vez que você abrir um terminal, adicione a linha acima ao seu arquivo de configuração do shell, como o `~/.bashrc` ou `~/.zshrc`, dependendo do seu shell.

```bash
echo "source /path/to/emsdk/emsdk_env.sh" >> ~/.bashrc
source ~/.bashrc
```

#### 4. **Verificar a Instalação**

Verifique se o Emscripten foi instalado corretamente executando o comando:

```bash
emcc -v
```

Se tudo estiver funcionando corretamente, ele deverá exibir a versão do Emscripten e outras informações.

#### 5. **Instalar o Python (se necessário)**

Emscripten também requer o Python para a construção. Caso você ainda não tenha o Python instalado, pode instalá-lo com o seguinte comando:

```bash
sudo apt install python3
```

---

### Conclusão

Agora que você instalou o **Emscripten** no Ubuntu, pode usá-lo para compilar projetos como o **OpenCV.js** ou outros projetos que necessitem converter código C/C++ para JavaScript.