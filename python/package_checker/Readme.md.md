````markdown
# 📦 pakchek — Package Checker

A simple Python script to check which of my go-to libraries are installed and generate a `requirements.txt`.

---

## 🔹 Usage
Run the script directly:

```bash
python check_packages.py
````

---

## 🔹 Script

```python
import importlib.metadata

packages = [
    "beautifulsoup4",
    "fastapi",
    "html5lib",
    "jinja2",
    "langchain",
    "langchain-astradb",
    "langchain_core",
    "langchain-google-genai",
    "langchain-groq",
    "lxml",
    "python-dotenv",
    "python-multipart",
    "selenium",
    "streamlit",
    "undetected-chromedriver",
    "uvicorn",
    "structlog",
    "langgraph",
    "ragas",
    "langchain-mcp-adapters",
    "mcp",
    "ddgs",
    "langchain-openai",
]

def main():
    # Print to console
    for pkg in packages:
        try:
            version = importlib.metadata.version(pkg)
            print(f"{pkg}=={version}")
        except importlib.metadata.PackageNotFoundError:
            print(f"{pkg} (not installed)")

    # Write requirements.txt
    with open("requirements.txt", "w") as f:
        for pkg in packages:
            try:
                version = importlib.metadata.version(pkg)
                f.write(f"{pkg}=={version}\n")
            except importlib.metadata.PackageNotFoundError:
                pass  # skip missing

if __name__ == "__main__":
    main()
```

---

## 🔹 Example Output

Console:

```
beautifulsoup4==4.13.0
fastapi==0.116.1
html5lib (not installed)
```

Generated `requirements.txt`:

```
beautifulsoup4==4.13.0
fastapi==0.116.1
jinja2==3.1.4
```

```