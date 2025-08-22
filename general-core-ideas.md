# General Core Ideas you should try

If you're working with Copilot, I recommend first adding a configuration file for the Copilot agent, located at:

`.github/copilot-instructions.md`

I suggest treating this file as a sort of project briefing. Hopefully, you’re familiar with Markdown, since in my experience it’s the “language” that AI works best with.

I recommend adding configuration files in subdirectories that require them. For example, we can have a `testing-guide.md` that serves as context so the agent knows how to handle the contents of the `tests` directory.

---

Are you speaking Javascript? If possible, document the code with JSDoc, especially for critical functions.

---

Tickets can leverage all this context, and depending on the IDE, AI models can manually load these files as context. For instance, in Copilot inside VSCode, you can directly add any Markdown file to the context before asking it a question.

> For Cursor IDE, you should take a look at the `Rules & Memories` tab on `Settings`. And play adding new doc at `Indexing & Docs`.

When creating a ticket (Project Backlog), if you want to request a broader solution instead of small portions, the more scope you want to cover, the more detailed the ticket must be. Otherwise, context may be lost. If the tasks are short, repetitive, or simple, the AI tends to handle them better with plain, everyday language.

---

I recommend communicating in Markdown whenever possible. AI does not interpret:

```plaintext
const [counter, setCounter] = useState(0);
```

the same way as:

````plaintext
  ```javascript
  const [counter, setCounter] = useState(0);
  ```
````

So far, I’ve had better results using Markdown syntax rather than plain text.

Lastly, something that really helps is to include in a comment which file the code belongs to. Example in `Login.tsx`:

```javascript
// Login.tsx

const [session, setSession] = useState(null);
```
