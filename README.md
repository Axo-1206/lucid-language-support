# Lucid Language Support

Editor support for the **Lucid Graph Format** — a declaration-only format for describing node graphs, resources, and enums. This extension provides syntax highlighting and snippets. It is **not** a language server, compiler, or type checker.

## Features

- **Syntax highlighting** for `.lucid` files:
  - Declarations: `import`, `enum`, `resource`, `node`
  - The `on` clause for trigger wiring
  - Attributes, including `@export`
  - Module qualification (`keys::Key`) and field access (`Key.W`, `Config.speed`)
  - Signed numeric literals (`-400.0`, `+7`, `-0xFF`)
  - Line comments (`-- …`) and nestable block comments (`/- … -/`)
  - Primitive types (`bool`, `char`, `string`, `int8`–`int64`, `uint8`–`uint64`, `float32`, `float64`)
- **Snippets** for every declaration form and common value shapes.

## File extension

Lucid source files use the **`.lucid`** extension.

> The old `.luc` extension is **deprecated** and no longer registered by this extension. Rename existing `.luc` files to `.lucid` to keep syntax highlighting.

## Example

```lucid
import core.keys

@export
enum Key {
    W,
    A,
    S,
    D,
}

@export
resource PlayerConfig {
    speed:      float = 200.0,
    jump_force: float = -400.0,
    max_hp:     int   = 100,
    key_left:   Key   = Key.A,
}

node speed    = Float32Node(200.0)
node input_x  = InputAxis1D(Key.A, Key.D)
node body     = BodyNode(player)
node on_hit   = OnCollision(body, "hazard")
node play_sfx = PlaySound("hit.wav") on on_hit