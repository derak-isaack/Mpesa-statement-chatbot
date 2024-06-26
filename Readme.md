## <div style="padding: 20px;color:white;margin:10;font-size:90%;text-align:left;display:fill;border-radius:10px;overflow:hidden;background-image: url(https://w0.peakpx.com/wallpaper/957/661/HD-wallpaper-white-marble-white-stone-texture-marble-stone-background-white-stone.jpg)"><b><span style='color:black'> M-PESA RAG application</span></b> </div>

![OpenAI](https://img.shields.io/badge/OpenAI-412991?logo=openai&logoColor=fff&style=for-the-badge)
![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=fff&style=for-the-badge)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?logo=jupyter&logoColor=fff&style=for-the-badge)

`RAG` application that uses `OpenAI embeddings` to allow user interaction with the `Safaricom PDF M-pesa statement` reports to analyze one's transactions patterns.

The application uses `llama-index` as the base for the `Retrieval Augmneted Generation` and `OpenAI` embeddings as the vector store for similarity search purposes. 

The model gets it wrong at some instances during vector inferencing & similarity search and therefore refining the queries or using the `LllamaParser` is necessary to produce quality results.

## <div style="padding: 20px;color:white;margin:10;font-size:90%;text-align:left;display:fill;border-radius:10px;overflow:hidden;background-image: url(https://w0.peakpx.com/wallpaper/957/661/HD-wallpaper-white-marble-white-stone-texture-marble-stone-background-white-stone.jpg)"><b><span style='color:black'> Improving accuracy</span></b> </div>

To improve the query results, it is very essential to use tools which clean the data for any `RAG` applications. One such tool is the `Llama_parser`. The main goal of `LlamaParse` is to parse and clean your data, ensuring that it's good quality before passing to any downstream LLM use case such as advanced RAG. To utilize the use of its 1000 pages free API, check the following ![docs](https://docs.llamaindex.ai/en/stable/llama_cloud/llama_parse/) and to get the code snippets for use, check ![this](https://cloud.llamaindex.ai/parse)

Below is a snippet showing the benefits of using the `LlamaParser`:
![LlamaParser](<Screenshot (1000).png>)

Running the command `pip install -r requirements.txt` installs all the required dependencies including the `LlamaParser`. To use this Parser, one remaining dependency is using the library `net-ascyncio` which can be installed using the command `pip install ascyncio`.

After using the `Parser` library, the search queries improve significantly. Especially for applications involving use of tables and figures. 

## <div style="padding: 20px;color:white;margin:10;font-size:90%;text-align:left;display:fill;border-radius:10px;overflow:hidden;background-image: url(https://w0.peakpx.com/wallpaper/957/661/HD-wallpaper-white-marble-white-stone-texture-marble-stone-background-white-stone.jpg)"><b><span style='color:black'> Approach II </span></b> </div>

Alternatively, instead of converting the pdf fully with `OpenAI` embeddings, the library `tabular-py` which extracts tables form pdfs and converts them to `CSVs` can be used. This library is a simple python wrapper for java-tables and their [documentation](https://tabula-py.readthedocs.io/en/latest/) is conclusive about all approaches. The library however requires `JAVA` be installed because it's a python wrapper for `JAVA`.

Below is a snippet about how the library achieves this:
![Tabular-py](<Screenshot (975).png>)

After conversion to a CSV, the use of `Pandas-AI` can now be employed to allow querying the data using user prompts. Their [documentation](https://docs.pandas-ai.com/examples) is also conclusive with a tone of code snippets with examples for querying:

* Excel files
* Google sheets
* CSVs

Below are the code snippets:
![CSV](images/Screenshot%20(976).png)
![Excel](<images/Screenshot (977).png>)
![Google Sheets](<images/Screenshot (978).png>)


It also employs use of various `API KEYS` which serve as credentials for interacting with the `Generative AI` models. 
