# Vim

## Tips

1. Do not quit vim each time you want to go back to your shell. Instead use `Ctrl+Z` and type 'fg' to go back to vim.
2. Insertion mode is only to type text not to move your cursor.
3. Stay on the home row, use `H`, `J`, `K` and `L` to move the cursor.
4. Map `Caps Lock` on `Escape`.
5. Use motions allow more intelligent movement and oprators act on the motion (delete, indent, copy...).

## Operators

- `c`: Change.
- `d`: Delete.
- `y`: Copy.
- `p`: Paste.
- `=`: Indent.
- `<`: Shift left.
- `>`: Shift right.
- `gu`: Make lowercase.
- `gU`: Make uppercase.

## Motions

- `0`: Beginning of line.
- `$`: End of line.

- `w`: Words forward.
- `b`: Words backward.

- `(`: Sentence backward.
- `)`: Setence forward.

- `i(`: Everything between parentheses.
- `a(`: Everything between parentheses (included).

- `iB`: Everything between brackets).
- `aB`: Everything between brackets (included).

## Selection

First go to visual mode using `v`.

...

## Search / replace

- `/pattern`: Search for a pattern.
- `n`: Repeat search in same direction.
- `N`: Repeat search in opposite direction.
- `:%s/old/new/g`: Replace all odd with new in the whole file.

## Windows (buffers)

- `:e filename`: Edit a file in a new buffer.
- `Ctrl-ww`: Switch between windows.

## Tabs

...
