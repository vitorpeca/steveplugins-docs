# FlyingCarpet — Guia do Administrador

Plugin de tapete voador para Minecraft Java Edition por **StevePlugins**.

---

## Requisitos

- Minecraft Java 1.20+
- Paper, Spigot, Folia ou Mohist
- Chave de licença válida (adquirida em steveplugins.com)

## Instalação

1. Coloque o arquivo `FlyingCarpet.jar` na pasta `plugins/` do servidor
2. Reinicie o servidor
3. Edite `plugins/FlyingCarpet/config.yml` e insira sua chave de licença
4. Rode `/tapete recarregar` ou reinicie o servidor

## Configuração

O arquivo `plugins/FlyingCarpet/config.yml` controla todas as opções:

```yaml
# Idioma: "pt" (português) ou "en" (inglês)
language: "pt"

# Sua chave de licença
license-key: "sua-chave-aqui"

# Velocidade de subida em blocos (1-5)
rise-speed: 1

# Velocidade de descida em blocos (1-5)
descend-speed: 1

# Intervalo de verificação em ticks (1 tick = 50ms)
check-interval-ticks: 2

# Tipo de bloco do tapete (nome do Material do Minecraft)
carpet-block: "GLASS"

# Mundos onde o tapete é permitido
enabled-worlds:
  - "world"
  - "world_nether"
  - "world_the_end"
```

## Idiomas

O plugin vem com português e inglês. Mude `language` no config.yml.

As mensagens ficam em arquivos editáveis:
- `plugins/FlyingCarpet/messages_pt.yml`
- `plugins/FlyingCarpet/messages_en.yml`

Você pode editar qualquer mensagem, cor e placeholder.

## Comandos

Todos os comandos funcionam em português e inglês.

| Comando | Alias | Descrição |
|---|---|---|
| `/tapete ativar` | `/carpet activate` | Ativa o tapete voador |
| `/tapete desativar` | `/carpet deactivate` | Desativa o tapete voador |
| `/tapete ajuda` | `/carpet help` | Mostra ajuda |
| `/tapete recarregar` | `/carpet reload` | Recarrega configuração |

Aliases do comando principal: `/carpet`, `/fc`

## Permissões

| Permissão | Padrão | Descrição |
|---|---|---|
| `flyingcarpet.use` | todos | Usar o tapete voador |
| `flyingcarpet.reload` | op | Recarregar configuração |
| `flyingcarpet.admin` | op | Permissão administrativa |

## Como Funciona

O tapete voador cria uma plataforma 3x3 de blocos de vidro abaixo do jogador:

- **Pular (espaço)**: o tapete sobe
- **Agachar (shift)**: o tapete desce
- **Andar**: o tapete acompanha o jogador horizontalmente

O tapete respeita construções existentes — blocos sólidos não são substituídos. Ao desativar ou sair do servidor, todos os blocos originais são restaurados automaticamente.

## Compatibilidade

O plugin é compatível com as seguintes plataformas de servidor:

- **Paper** (recomendado)
- **Spigot**
- **Mohist**
- **Folia**

Versão mínima: Minecraft 1.20+

## Soft-Dependencies (opcionais)

O plugin detecta automaticamente os seguintes plugins de proteção, quando instalados:

- **GriefPrevention** — o tapete não coloca blocos em terrenos onde o jogador não tem permissão de construção
- **WorldGuard** — o tapete respeita regiões protegidas onde o jogador não pode construir

Esses plugins são opcionais. O FlyingCarpet funciona normalmente sem eles.

## Suporte

- Site: steveplugins.com
- Problemas com licença: verifique a chave no config.yml
- Erros: consulte o log do servidor em `logs/latest.log`
