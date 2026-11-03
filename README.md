# TogsBoost 2: Releases

Este repositório existe **apenas para distribuir os instaladores** do TogsBoost 2.
Não há código-fonte aqui: o código é privado.

Os instaladores do TogsBoost 1 ficam em outro repositório,
[togsboost-proj/togsboost-releases](https://github.com/togsboost-proj/togsboost-releases).
Os dois são separados de propósito: o app do TogsBoost 1 nunca enxerga uma versão
do TogsBoost 2, e o contrário também vale.

## Baixar

Use sempre o link oficial, que aponta para a versão mais recente:

https://www.togsboost.com.br/dois/baixar

O link direto do arquivo também é estável:

```
https://github.com/togsboost-proj/togsboost2-releases/releases/latest/download/TogsBoost2-Setup.exe
```

## Como uma release é publicada

O build sai do repositório privado do código, via `pnpm run build:release`.

Cada release carrega estes arquivos:

| Arquivo | Para que serve |
|---|---|
| `TogsBoost2-Setup.exe` | O instalador que o link de download entrega (cópia com nome fixo) |
| `togsboost-<versão>-setup.exe` | O mesmo instalador, com a versão no nome, que o app instalado baixa ao atualizar |
| `latest.yml` | Como o app instalado descobre que há versão nova |
| `togsboost-<versão>-setup.exe.blockmap` | Permite baixar só a diferença ao atualizar |
| `TogsBoost-<versão>-win.zip` | O app compactado, sem instalador |

Apagar `latest.yml` de uma release quebra a atualização automática de quem já tem o app.
Sem `TogsBoost2-Setup.exe` na release mais recente, o link de download dá 404.
