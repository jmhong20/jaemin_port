Step 1: Create a new virtual environment
- `python -m venv <name>`

Step 2: Activate the virtual environment
- `source <name>/bin/activate # Linux`
- `.\<name>\Scripts\activate # Windows`

Step 3: Install dependencies and add virtual environment to the Python Kernel
- `python -m pip install --upgrade pip`
- `pip install ipykernel`
- `python -m ipykernel install --user --name=<name>`
