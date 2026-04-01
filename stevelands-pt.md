# SteveLands — Guia do Administrador

Plugin de terrenos protegidos para Minecraft Java Edition por **StevePlugins**.

---

## Requisitos

- Minecraft Java 1.20+
- Paper, Spigot, Folia ou Mohist
- GriefPrevention instalado no servidor
- Chave de licença válida (adquirida em steveplugins.com)

## Instalação

1. Coloque o arquivo `SteveLands.jar` na pasta `plugins/` do servidor
2. Reinicie o servidor
3. Edite `plugins/SteveLands/config.yml` e insira sua chave de licença
4. Rode `/terreno recarregar` ou reinicie o servidor

## Configuração

O arquivo `plugins/SteveLands/config.yml` controla todas as opções:

```yaml
# Idioma: "pt" (português) ou "en" (inglês)
language: "pt"

# Sua chave de licença
license-key: "sua-chave-aqui"

# Tamanhos de terreno disponíveis (em blocos)
claim-sizes:
  - 10
  - 20
  - 50

# Máximo de terrenos por jogador
max-claims-per-player: 3

# Tempo de espera entre compras (segundos)
cooldown-seconds: 60

# Mundos onde terrenos são permitidos
enabled-worlds:
  - "world"
  - "world_nether"
  - "world_the_end"

# Cooldown de notificação de entrada (segundos)
entry-notification-cooldown-seconds: 5

# Casas por tamanho de baú
# "default" = casa padrão | "none" = sem casa | "nome" = schema customizado
chest-schemas:
  10: "default"
  20: "default"
  50: "default"
```

## Idiomas

O plugin vem com português e inglês. Mude `language` no config.yml.

As mensagens ficam em arquivos editáveis:
- `plugins/SteveLands/messages_pt.yml`
- `plugins/SteveLands/messages_en.yml`

Você pode editar qualquer mensagem, cor e placeholder.

## Comandos

Todos os comandos funcionam em português e inglês.

| Comando | Alias | Descrição |
|---|---|---|
| `/terreno comprar <tamanho>` | `/land buy <size>` | Compra um terreno |
| `/terreno lista` | `/land list` | Lista seus terrenos |
| `/terreno ajuda` | `/land help` | Mostra ajuda |
| `/terreno recarregar` | `/land reload` | Recarrega configuração |
| `/terreno dar <jogador> <tamanho> [qtd]` | `/land give` | Dá baú de terreno |
| `/terreno schema pos1` | — | Marca canto 1 do schema |
| `/terreno schema pos2` | — | Marca canto 2 do schema |
| `/terreno schema salvar <nome>` | `save` | Salva schema |
| `/terreno schema lista` | `list` | Lista schemas |

Aliases do comando principal: `/land`, `/stevelands`, `/sl`

## Permissões

| Permissão | Padrão | Descrição |
|---|---|---|
| `stevelands.buy` | todos | Comprar terrenos |
| `stevelands.list` | todos | Listar terrenos |
| `stevelands.reload` | op | Recarregar config |
| `stevelands.give` | op | Dar baús de terreno |
| `stevelands.admin` | op | Criar/gerenciar schemas |
| `stevelands.bypass.limit` | ninguém | Ignorar limite de terrenos |
| `stevelands.bypass.cooldown` | ninguém | Ignorar cooldown |
| `stevelands.claims.<N>` | ninguém | Define limite customizado (ex: `stevelands.claims.5` = 5 terrenos) |

### Limites por Permissão (VIP)

Use permissões no formato `stevelands.claims.<número>` pra definir limites diferentes por grupo:

| Grupo | Permissão | Limite |
|---|---|---|
| Jogador comum | (nenhuma) | Usa o valor do config.yml (padrão: 3) |
| VIP | `stevelands.claims.5` | 5 terrenos |
| VIP+ | `stevelands.claims.10` | 10 terrenos |
| Admin | `stevelands.bypass.limit` | Ilimitado |

O plugin usa o maior valor de permissão encontrado. Configure no LuckPerms ou plugin de permissões do seu servidor.

## Baú de Terreno

O baú de terreno é um item especial que, ao ser colocado no chão:
1. Cria um terreno protegido centrado na posição
2. Coloca cercas de madeira na borda
3. Gera uma casa starter (ou schema customizado)

Para dar baús aos jogadores:
```
/terreno dar NomeDoJogador 20 1
```

Para integrar com plugins de kits, use o comando acima na configuração do kit.

## Schemas Customizados

Schemas permitem criar casas personalizadas para cada tamanho de terreno.

1. Construa a casa desejada no jogo
2. Vá para o canto inferior da construção: `/terreno schema pos1`
3. Vá para o canto superior oposto: `/terreno schema pos2`
4. Salve: `/terreno schema salvar casa-vip`
5. No config.yml, associe ao tamanho:
```yaml
chest-schemas:
  10: "casa-pequena"
  20: "casa-media"
  50: "casa-vip"
```

## Notificações de Entrada

Quando um jogador entra em um terreno:
- O visitante vê o nome do dono na ActionBar
- O dono recebe uma notificação de quem entrou
- Notificações têm throttle configurável para evitar spam

Quando um jogador sai de um terreno:
- Recebe uma mensagem na ActionBar informando que saiu

## Suporte

- Site: steveplugins.com
- Problemas com licença: verifique a chave no config.yml
- Erros: consulte o log do servidor em `logs/latest.log`
