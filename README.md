# RetroCloud Lab

Este projeto usa Nginx (via Docker) para servir um site de emuladores que rodam no navegador do usuário (WebAssembly/EmulatorJS).

**Arquitetura:** Este projeto usa um único container Nginx para servir arquivos estáticos. Não há containers separados por emulador (ex: Debian + Supervisor), pois essa é uma arquitetura para "Cloud Gaming" (streaming de vídeo), que não é o caso aqui. Todo o processamento do emulador ocorre no navegador do usuário.

## PASSOS OBRIGATÓRIOS

O script não pode baixar os emuladores nem os jogos. Você DEVE fazer o seguinte:

### 1. (OBRIGATÓRIO) Baixar o EmulatorJS

1.  Vá ao site `emulatorjs.com` e baixe o pacote `.zip` completo.
2.  Descompacte o `.zip`.
3.  **Arquivos .js:** Copie os arquivos como `emulator.js`, `utils.js`, etc., para a pasta `web/js/emulator/`.
4.  **Arquivos .wasm:** Copie os "cores" (ex: `snes9x_libretro.wasm`) para a pasta `web/colors/`.

### 2. (OBRIGATÓRIO) Adicionar suas ROMs

O `index.html` já está configurado para procurar jogos específicos.

1.  Coloque sua ROM do Super Mario World em `web/roms/snes/mario.smc`
2.  Coloque sua ROM do Mario 64 em `web/roms/n64/mario.n64`
3.  Coloque sua ROM do Crash Bandicoot em `web/roms/ps1/crash.chd` (PS1 funciona melhor com .chd)

### 3. Iniciar o Servidor

Com o Docker e o Docker Compose instalados, rode:

```bash
docker-compose up --build -d
```

### 4. Acessar

Abra seu navegador em `http://localhost:8080`.
