# kha_interleaved_layout

Output:
![](img.png)

Relevant to D3D11, to make deinterleaved buffers work:

`pipeline.interleavedLayout = false;`

Right now Kha assumes instanced rendering when passing multiple structures into input layout (atleast in D3D11 backend):

`pipeline.inputLayout = [structure, structureInstanced, ...];`

Fixing that should get rid of the interleavedLayout flag:

`pipeline.inputLayout = [structure1, structure2, structureInstanced];`
