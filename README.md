> "Needs more computer science, less noise."
> --Nick Szabo

Bitcoin Notebook connects [Rusty Russell's `bitcoin-iterate`](https://github.com/rustyrussell/bitcoin-iterate/) to the Jupyter iPython Notebook to enable fast and easy processing and graphing of `bitcoin-iterate` queries against the blockchain history in a way that is reproduceable and literate.

Check out the [example notebook](./notebooks/Bitcoin Notebook Hello World.ipynb) which contains demonstration queries, and a [PDF "paper" export](./notebooks/Bitcoin Notebook Hello World.pdf) of the same results.

Use
---

	from bi import bi
	result = bi("--block %bl --end=140000")
	plt.figure(figsize=(20,8))
	plt.plot(result["results"]["%bl"], label="%bl")
	plt.show()

![Example query result](./notebooks/example-query.png)

Install
-------

Run `make` to generate the Python virtualenv environment and compile `bitcoin-iterate`.

Run
---

`./bitcoin-notebook` will launch the Jupyter server with the paths all configured correctly and open a browser window pointing at the notebook list.

Probably the most important thing to remember for people new to Jupyter is that pressing `shift-Enter` will re-run the code in the highlighted section.

Dependencies
------------

You can run `make dependencies` if you're on a Debian based system. Otherwise the packages you will need before the virtualenv will deploy are:

	* libfreetype6-dev
	* liblapack-dev
	* gfortran
	* libpng12-dev

Run `make dependencies-pdf` to install the packages required for exporting to PDF. Here are the packages that will be installed:

	* texlive-latex-base
	* texlive-latex-extra
	* texlive-fonts-recommended
	* pandoc
	* http://ctan.mackichan.com/macros/plain/contrib/misc/ulem.sty

