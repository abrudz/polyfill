# polyfill
 One-letter implementation of missing or extended Dyalog APL primitives.

| Polyfill Letter | Ideal Symbol | Meaning                                                      |
| --------------- | ------------ | ------------------------------------------------------------ |
| `I`             | `⊇`          | [From](https://apl.wiki/From) including [scatter-point extension](https://aplwiki.com/wiki/From#Scatter-point) |
| `V`             | `∨`          | Sort-descending                                              |
| `A`             | `∧`          | Sort-ascending                                               |
| `F`             | `⫽`          | [Replicate ("Filter") First](https://aplwiki.com/wiki/Replicate) as pure function |
| `E`             | `⑊`          | [Expand First](https://aplwiki.com/wiki/Expand) as pure function |
| `R`             | `⍴`          | [Reshape](https://apl.wiki/Reshape) allowing `¯1` to auto-shape axis and chop excess, `¯2` to require exact fit, `¯3` to recycle elements, `¯4` to use fill elements |
| `S`             | `$`          | String interpolation using  `${apl expression}`              |
| `T`             | `⊤`          | `⊥⍣¯1`                                                       |
| `ë`             | `⸚`          | [Each](https://aplwiki.com/wiki/Each) which, if any argument is empty, doesn't apply its operand but rather returns an appropriately shaped no-prototype array |
| `Ö`             | `⍥`          | Depth: apply left operand at leaves of depth no greater than right-operand, or, if right operand is negative, no more than that many levels from the argument's max depth |

Naming convention:

* Uppercase: function
* Lowercase with dieresis (`¨`): monadic operator
* Uppercase with dieresis (`¨`): dyadic operator

## Usage

Options:

* Copy the (long) middle line of polyfill.dyalog into your code to define polyfills there
* `'#'⎕NS 0⎕FIX'file://path/polyfill.dyalog'` to load from file into `#` (or replace `#` with other target namespace)
* `⎕FIX'file://path/polyfill.dyalog'` to create namespace called `p_` with polyfills in it.
* `#.⎕FIX'file://path/polyfill.dyalog'⋄⎕PATH←'#.p_'` to make all the polyfills available from all namespaces, but note that polyfills need extra syntax to be used in modified assignments and on pass-through values from assignments, e.g. `var(⊢I)←value`  and  `A⊢var←value` 

