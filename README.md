# The `maltrino` layout

The `maltrino` layout is a reimagination of the pioneering `malt` layout that [Lillian Malt](http://www.maltron.com/lillian-malt-papers.html) created for the eponymous [Maltron ergonomic keyboard](https://www.wikiwand.com/en/Maltron). The name `maltrino` is a [pun](https://en.wikipedia.org/wiki/Superpartner) on `maltron`.

The core design principle of `maltrino` is to take a more balanced approach between ergonomic considerations and layout "efficiency" as measured in modern metrics (see, e.g., [keysolve](https://clemenpine.github.io/keysolve-web/) and the [AKL doc](https://bit.ly/keyboard-layouts-doc)). Some characteristics are:
1. Keep the nine home keys of `malt`, including the signature `e`-on-thumb.
2. Skew non-homerow use of middle, ring, and pinky fingers to either the top or the bottom row, instead of distributing evenly between the two. In practice, this means these fingers mostly move between two rows instead of three, which minimizes both finger travel, and the frequency of Scissor Bigrams (such as qwerty `cr`, with one letter on the middle finger in a row lower than the other letter, which are known to cause discomfort).
3. Have all vowels on the same hand, to promote hand alternation.
4. Reduce Lateral Stretch Bigrams (such as qwerty `get`, which are consecutive key presses that involve both the outer index column and the middle finger), sometimes at the cost of slightly higher Same Finger Bigrams (e.g., the placement of `y`). SFB mitigation is discussed toward the end.
5. Healthy pinky usage (around 9% on both sides).
6. No vowel clustering/stacking as employed by many modern layouts (where all vowels are clustered into three fingers, to relax SFB constraints by the 4th finger -- typically the index -- on the vowel hand), thanks to the thumb-`e`. Vowel clustering typically incurs heavy load on the respective fingers, but is useful in improving "optimizer score", as we briefly entertain toward the end.


## Main Layout
```
                   k
# , u c #      b m d l p
a o i s y      f t h r n
' z . g #      v w x q j
         e   spc
```
Note: `#` denotes unassigned keys, `spc` is the space key, and `k` is assigned to the number row.

### Minor rearrangements:
For use without the number row `k` (due to lack of physical keys, too far of a reach, etc.), the following variant is suggested:
```
q , u c #      b m d l p
a o i s y      f t h r n
' z . g #      v w k x j
         e   spc
```

For those who can tolerate more bottom row usage, one or both of the following additional swaps can be employed to reduce the load on the right index:
- `b <-> k`
- `v <-> x`

For those who cannot tolerate `k` on middle finger bottom row (due, e.g., to`k_d` skipgrams or `kl/lk` scissor bigrams, both of which hop over the home row), the following variant is suggested:
```
' , u c #      b m d l p
a o i s y      f t h r n
k z . g #      v w x q j
         e   spc
```

See this variant in action [here](https://youtu.be/IivLDfUq64o) and [here](https://youtu.be/YguKZIDKrBw)

## Alternative consonant hand
Swapping `t <-> h` and `w <-> d` results in an alternative consonant hand:
```
q , u c #      b m w l p
a o i s y      f h t r n
' z . g #      v d k x j
         e   spc
```
`f,m,d` shuffles can be employed at will.  Note how the `m w f t h r d` group recovered their `dvorak` fingering.

## "Optimizing" for analyzers
It is possible to "optimize" the layout further, using tricks such as vowel stacking and increased bottom row/pinky usage, to (sometimes significantly) improve analyzer scores. The following variation would still be quite usable, but perhaps not as comfortable and ergonomic:
```
, o y c #      k f w l p
u a i s #      m h t r n
. # x g #      j d v q b
         e   spc
```
Note that `z` is missing but can be put at any of the unassigned keys due to its extremely low frequency. `'` is not included but can be safely placed to the right of `g` to allow alt-fingering. Swapping `b/p <-> j` brings down right pinky usage but probably at the cost of analyzer scores.

## SFB mitigation
The remaining SFBs can be quite efficiently mitigated with modern programmable keyboards. One technique is to use Transient Layers, which are temporarily activated after the first letter of an SFB is typed. For example, after pressing any key in the `c s g` column, one could activate a layer on which `z -> c` and `' -> y`. This relieves `[csg]y` and `sc` SFBs. The transient remappings are chosen for the bigrams without the remapping to be statistically unlikely -- in the worst case scenario, one could simply wait for the transient layer to expire (configurable in most firmwares). Combos is another technique that may be easier to program and faster to execute (e.g., assigning the combo `md` to output `mb`), although it may require some cognitive effort to read a couple extra letters ahead.
