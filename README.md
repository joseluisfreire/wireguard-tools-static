# wireguard-tools-static

wireguard-tools compilado estaticamente (Linux amd64) para uso no addon WireGuard do MK-AUTH.

# wireguard-tools-static

Binários **compilados estaticamente** do [wireguard-tools](https://git.zx2c4.com/wireguard-tools/) para **Linux amd64** — prontos para uso em sistemas como o MK-AUTH TUX 6.12 (Devuan), sem dependências externas.

---

## 📦 O que contém

| Binário | Descrição |
|---------|-----------|
| `wg` | Ferramenta de configuração de interfaces WireGuard |
| `wg-quick` | Script para gerenciamento rápido de túneis WireGuard |

Ambos compilados com **musl libc** (linkagem estática), sem necessidade de bibliotecas do sistema.

---

## 🔗 Código-Fonte Original

> **Este repositório NÃO contém código-fonte modificado.**
> Apenas distribui binários pré-compilados para conveniência.

O código-fonte oficial do wireguard-tools é mantido por **Jason A. Donenfeld** e está disponível em:

### 👉 [https://git.zx2c4.com/wireguard-tools/](https://git.zx2c4.com/wireguard-tools/)

Mirror no GitHub: [https://github.com/WireGuard/wireguard-tools](https://github.com/WireGuard/wireguard-tools)

---

## 🔨 Compile Você Mesmo

Se preferir compilar a partir do fonte oficial (recomendado para ambientes de produção críticos), o processo é simples:

```bash
# Instalar dependências de compilação
apt install -y build-essential musl-tools git

# Clonar o fonte oficial
git clone https://git.zx2c4.com/wireguard-tools/
cd wireguard-tools/src

# Compilar estaticamente com musl
make CC=musl-gcc LDFLAGS="-static"

# Verificar
file wg
# wg: ELF 64-bit LSB executable, x86-64, statically linked, ...

# Instalar onde quiser
cp wg /usr/local/bin/
cp wg-quick/linux.bash /usr/local/bin/wg-quick
chmod +x /usr/local/bin/wg /usr/local/bin/wg-quick

> 💡 **Dica**: compilar do fonte oficial é a forma mais segura de garantir
> a integridade dos binários. Este repositório existe apenas como
> conveniência para o projeto [WireGuard VPN Addon para MK-AUTH](https://github.com/joseluisfreire/WireGuard-VPN-Addon).

---

## 📄 Licença

O wireguard-tools é licenciado sob **GPL-2.0** por [Jason A. Donenfeld](https://www.jasondonenfeld.com/).

Consulte o arquivo [LICENSE](LICENSE) para o texto completo e [NOTICE](NOTICE) para detalhes de atribuição.

**"WireGuard"** é uma marca registrada de Jason A. Donenfeld.
