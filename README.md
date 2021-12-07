# FcPanGen
## Description
Studies on cellular immunity largely depend on multi-color flow cytometry. One of the challenges in the application of multi-color flow cytometry is to decide on a staining panel to discriminate the cells of interest. FcPanGen is a commanline tool that generates a list of markers for the identification of provided immune cell type names (i.e., gdT, NKT, Neutrophil, etc.) and provides a gating strategy (recursive gatings) for human samples.
## Usage
You can either provide cell names in a .txt file or insert the names on the terminal one by one. 
<pre><code>$ FcPanGen -mg < file_name ></code></pre>
<pre><code>$ FcPanGen -mg < cell_type1; cell_type2; ... ></code></pre>
*-m* option provides the optimal list of markers (expression is shared less with other cell types) that can be used together to identify cells of interest. If it is not used FcPanGen will provide the list of markers expressed by provided cell type(s).

*-g* option provides a gating strategy as below:
<pre><code>
CD45+CD66- --> CD3+CD20- --> TCRb+gdTCR- --> CD4+CD8- --> CD4+T-bet+ == Th1
           --> CD3-CD20+ --> CD69high Bcl6+ == Fol_B
                         --> CD69- Bcl6+ ==  GermCent_B     
</code></pre>
 

**Note that the cell names should be provided as indicated in the [cell_list.txt](https://github.com/ym-ibg/FcPanGen/blob/main/Cell_list), otherwise you will see a error message *"err: Unknown cell type"*.**
FcPanGen can generate more than one panel alternative for a particular cell type. To obtain multiple panels with different markers one can use *"-a < cell_type >"* option. Note that if you do not provide cell type, FcPanGen will try to provide all the possible combinations of panels and, most probably, eventually crush. 
