# Converting Google’s ADK Agent Team Colab Code to VS Code

I made a [screencast](https://www.youtube.com/watch?v=9RfT1jJqZZg&t=126s) showing how to run through Google’s ADK agent team example, as shown in their blog post,
[**Building Multi-Agent Teams with Google's Agent Development Kit**](https://developers.googleblog.com/2024/03/building-multi-agent-teams-with-adk.html)

The blog post walks through everything in Colab. Colab is great for testing and learning how things work.  

But I wanted to show how you could use the new ADK in a **production environment**, in case you want to actually build and deploy your own agents.

While doing that, I came across [Google’s official ADK GitHub repo](https://github.com/google/adk-python), which gives you the full Python version for local development.

---

## Key Differences Between Colab and VS Code

Imports, file paths, and how you run the code are a little different outside of Colab.  
You can apply these ideas often, so I thought it was worth noting them here:

- **Colab uses `!pip install` in a cell**, which needs to be re-run if you restart the runtime.
- In VS Code, you install dependencies once using the terminal, and they persist across sessions.
- **Notebook-specific imports** (like `IPython.display`) can usually be removed in VS Code.
- **File paths** are different — Colab often uses `/content/`, while local scripts should use `os.path` or `pathlib`.
- In Colab, you run cells one at a time. In VS Code, you typically run the whole script using:
```
  python main.py
```

### Installing Dependencies in VS Code

Instead of running !pip install in a notebook cell, you can install dependencies from a requirements.txt file like this:

```
pip install -r requirements.txt
```
Make sure you're in the same folder as requirements.txt when you run that command.
