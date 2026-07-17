# project-template

## Environment Setup (Example of `uv` project)

1. Install [uv](https://docs.astral.sh/uv/) if you haven't.

2. Setup and activate the Python virtual environment for this project:

```bash
uv init
uv run main.py
source .venv/bin/activate
```

You can exit the virtual environment by running `deactivate`.

## Development Notes - TODO: remove when publishing

Steps for using this template:

1. Replace `todo_pkg_name` across the project to your package name (based on the project name).
  * Only lower case letters, numbers, and `_` (not recommended) are allowed in the package name; do NOT use other symbols.
  * Prefer concise names and acronyms, e.g., `teco` instead of `test_completion`.
  * Don't forget to rename the `src/todo_pkg_name` directory.

2. Replace other `TODO`s in `pyproject.toml` and `README.md`, this can be done as you go along the project.

3. Test out your environment. Follow the Environment Setup instructions, and then...
  * Run `python -m todo_pkg_name.example_main --help` and see if the code runs (it should work from anywhere)
  * Run `pytest` to see the tests running (it must be run from the project root `/` or under `/tests`)

4. Notes about bundled dependencies:

   * `seutil` is a util library. There are some examples to use it in `example_main.py`.
     * In particular, `jsonargparse`, which is transitively installed by `seutil`, helps to parse command line arguments. Use it to read paths to inputs/outputs from command line, and avoid hardcoding them in code.
   * `ruff` is code formatter + linter. Run it periodically to improve your code quality.
     * Format code: `uv run ruff format .`
     * Lint code: `uv run ruff check .` (use `--fix` to auto-fix safe issues)
     * VS Code: install `charliermarsh.ruff` plugin; suggestions should show up in the editor
   * `ty` is static type checker (currently in beta; rules and diagnostics may evolve).
     * Type check: `uv run ty check`

5. Start developing your code.
  * If you need to add new dependencies, add them with `uv add <package_name>`; you may need to run `uv sync` to synchronize the virtual environment if you work on multiple machines. Details see [uv documentation](https://docs.astral.sh/uv/concepts/projects/dependencies/).
  * Follow formatting conventions: `uv run ruff format .`
  * Follow linting rules: `uv run ruff check .`
  * Write [type hints](https://docs.python.org/3/library/typing.html) and check with `uv run ty check`.
  * Write docstrings and tests.
  * Update this README as you work on the project, e.g., update summaries, add usage instructions, etc.


Reference: [pengyunie/python-template](https://github.com/pengyunie/python-template)