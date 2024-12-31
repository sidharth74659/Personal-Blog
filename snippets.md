
1. [js-snippets](./js)
2. [css-snippets](css.md)
3. [git-snippets](./git.md)
4. [exporting-copilot-chat-sessions-in-vscode-as-md](./snippets/exporting-copilot-chat-sessions-in-vscode-as-md.md)
5. [export-twitter-bookmarks](./snippets/export-twitter-bookmarks.md)


---

**Handling *address already in use*:**

```
Error: listen EADDRINUSE: address already in use :::3000
```

The error EADDRINUSE: address already in use :::3000 indicates that port 3000 is already being used by another process. You can either stop the process using port 3000 or change the port your Express.js server is using.

1. Find the Process: Use the following command to find the process using port 3000:
```
lsof -i :3000
```
2. Kill the Process: Once you have the process ID (PID), you can kill it using:
```
kill -9 <PID>
```

Or, Change the Port in Your Express.js app.

---

**Find Installed Java Versions:**

```sh
/usr/libexec/java_home -V
```

---

**Check Docker disk usage:**

```
docker system df
```

---

