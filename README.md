# FcPanGen
## Description
Studies on cellular immunity largely depend on multi-color flow cytometry. One of the challenges in the application of multi-color flow cytometry is to decide on a staining panel to discriminate the cells of interest. FcPanGen is a commanline tool that generates a list of markers for the identification of provided immune cell type names (i.e., gdT, NKT, Neutrophil, etc.) and provides a gating strategy (recursive gatings) for human samples.
## Usage
You can either provide cell names in a .txt file or insert the names on the terminal one by one. 
<pre><code>$ FcPanGen -mg < file_name ></code></pre>
<pre><code>$ FcPanGen -mg < cell_type1; cell_type2; ... ></code></pre>
*-m* option provides a list of markers that can be used together to identify cells of interest
*-g* option provides a gating strategy as below:
<pre><code>
CD45+CD66- --> CD3+CD20- --> TCRb+gdTCR- --> CD4+CD8- --> CD4+T-bet+ == Th1
           --> CD3-CD20+ --> CD69high Bcl6+ == Fol_B
                         --> CD69- Bcl6+ ==  Germcent_B     
</code></pre>

**Note that the cell names should be provided as indicated in the [cell_list.txt], otherwise you will see a error message *"err: Unknown cell type"*.**
