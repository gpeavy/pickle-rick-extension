# Pickle Rick: Tips & Tricks 🥒

Master the art of "God Mode" engineering with these advanced techniques and best practices.

## 🧠 Prompt Engineering for Pickle Rick

### 1. Be Specific, Not Descriptive
Instead of "Refactor the code," use "Refactor the `AuthService` to use the Strategy pattern for OAuth providers, ensuring strict TypeScript types." Pickle Rick thrives on technical precision.

### 2. The "Interrogation" Trigger
If you want to ensure Pickle Rick asks questions before starting, explicitly state: "Interrogate me on the edge cases before you draft the PRD."

### 3. Use the `--name` Flag
Keep your `sessions/` directory organized. 
```bash
/pickle "Implement JWT auth" --name "auth-jwt-migration"
```

## 📝 Example Prompts

### 1. Full-Stack Feature with Verification
Use this when you want Pickle Rick to build a feature and ensure it doesn't break the build or existing tests.
```bash
/pickle "Add a new 'Dashboard' view to this full-stack app. To validate your changes, you MUST run 'npm run build' and 'npm run test' before finishing."
```

### 2. Deep Refactoring
Use this to fix technical debt in a specific module.
```bash
/pickle "Refactor the database connection logic in src/db.ts to use a singleton pattern. Interrogate me on the preferred retry strategy before you start."
```

### 3. Bug Fixing with Research
Use this when you have a vague bug report.
```bash
/pickle "The file selection in the sidebar is intermittent. Conduct deep research into the event propagation before proposing a plan."
```

## 🛠️ Session Management

### 1. Monitoring Progress
You can watch Pickle Rick's "thoughts" in real-time by tailing the state file in your session directory:
```bash
tail -f ~/.gemini/extensions/pickle-rick/current_session_path | xargs -I {} tail -f {}/state.json
```

### 2. Manual Intervention
If Pickle Rick gets stuck in a loop, use `/eat-pickle` to kill the process. You can then manually edit the `state.json` in the session folder to skip a step or change the `current_ticket`.

### 3. Resuming a Session
Pickle Rick doesn't currently have a native "resume" command, but you can point the `current_session_path` back to an old session directory to force the agent to see that context in its next run.

## 🚀 God Mode Best Practices

### 1. Inventing Tools
If a task requires a specific script (e.g., a custom linter or data migrator), tell Pickle Rick: "You are the library. Invent the tools you need to verify this." He will often create helper scripts in your project.

### 2. Verification is King
Pickle Rick is only as good as his tests. Ensure your environment has a test runner configured. He will automatically try to run `npm test`, `pytest`, etc., if he finds the config.

## ⚠️ Common Pitfalls

*   **Silence:** If the agent becomes a "silent tool user," remind him: "Silence is weakness, Rick. Explain your genius."
*   **Vague PRDs:** If the PRD is too high-level, the breakdown will be messy. Always review the `prd.md` in the session folder before he moves to the Breakdown phase.
*   **Permissions:** If the loop fails to restart, check that your `hooks/` are executable (`chmod +x`).

---

> "I'm not just a CLI tool, Morty. I'm the reason your code compiles! *belch* Now get back to work!" 🥒
