# Termin
Termin is designed to be an easy to use cli maker that uses the modernic ``async`` and ``await`` syntax.

This library aims to make it simple for you to make your own CLI and provide
all the utilities and functions you need to help make this job easier.

## Installation
Use the package manager [pip](https://pip.pypa.io/en/stable/) to install Termin.

```bash
pip install termin
```

## Usage
```python
# Import the cli parser
import termin

# Instantiate a parser instance
parser = termin.Termin()

# Register the command to the parser
@parser.command('hello', describe=termin.Describe(usage=termin.Usage('Prints hello world', arguments=[]))) # leave arguments empty as there are no arguments
async def hello(ctx: termin.Context) -> None:
    # Respond with "Hello, World!"
    await ctx.print("Hello, World!")

# Register an echo command to the parser
@parser.command('echo', describe=termin.Describe(usage=termin.Usage('Echo the given text', arguments=[termin.Argument('text', 'The text to print')])))
async def echo(ctx: termin.Context) -> None:
	# Get the text argument
	text = ctx.get_argument('text')

	# Respond with the text
	await ctx.print(text)

# Run the parser
parser.run(args=sys.argv[1:])
```

## Issues
If you find any bugs, issues, or unexpected behaviour while using the library,
you should open an issue with details of the problem and how to reproduce if possible.
Please also open an issue for any new features you would like to see added.

## Contributing
Pull requests are appreciated, but not required.
If it is a breaking change, please open an issue discussing the change.

This is not required but, if you like the project, please star the repository on GitHub. It'll let me know i'm going the correct way!

## Links
- **License:** [MPL2.0](https://choosealicense.com/licenses/mpl-2.0/)
- **Repository:** [GitHub](https://github.com/FrostiiWeeb/termin)
- **Documentation:** [ReadTheDocs](https://termin.readthedocs.io/en/latest/) NOT WORKING AT THE MOMENT
