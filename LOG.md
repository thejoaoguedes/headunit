# Log — Central YT5760B / AC8259 (XYAUTO 1.73.7)

Regras: só `pm disable-user --user 0` (reversível). Sem uninstall, sem /system, sem root, sem flash.

## 2026-11-25 — Pesquisa inicial (nenhuma alteração na central)

Fonte: https://sites.google.com/view/yt5760bac8259. O tópico do XDA, 4171219, bloqueia acesso automatizado (desafio anti-bot), então foi lido só por resultados de busca.

- Android real: "Only real Android 9, even if it's advertised with higher versions" (página Home). FAQ: "Will firmware ever move beyond 'real' Android 9? Unlikely."
- Versões de 2/4 GB: "only 32bit Android".
- Opções de desenvolvedor: "Tapping Android build number 10x turns on developer mode until 1.75.* firmware" (página Menus & Settings). O 1.73.7 está nessa faixa.
- Car Settings → Factory Settings: senha `8888`.
- Factory Settings → Engineering Test Debugging: senha `26959910` (modos de energia; NÃO mexer).
- Factory Settings → USB Settings → Engineering Mode (segurar para entrar).
- USB: o 6 pinos aceita USB3 (o padrão é USB2). Para Android Auto por cabo, a porta precisa estar em modo **host**.
- Firmware: risco de brick por `logo.mrf` errado em pacotes OTA/UI. Não fazer flash.
- ZLink: ativação por licença; formatar ou resetar pode perder a ativação offline. Não mexer nos dados do ZLink.
- Áudio: o DSP padrão tem graves muito altos (preset "Rock" é mais equilibrado). Chamadas pelo ZLink têm mais atraso que pelo Bluetooth.
- Wi-Fi fica mais rápido com o Bluetooth desligado (interferência).

## Passo 1 — Conexão ADB (em andamento)

Estado ORIGINAL de Factory Settings → USB Settings (foto de 2026-11-25, 20:07), para reverter:
- usb port1 protocol: `usb3_0`
- usb port0 protocol: `usb2_0`
- usb mode: `host` (marcado)
- carplay i2c bus: marcado
- Engineer mode: desmarcado
- USB0 DVR Enhancement / USB1 DVR Enhancement / QB airplane mode: o estado não aparece na foto
