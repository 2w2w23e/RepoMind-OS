# Writeback Checklist

Before writing durable repository state, check:

- Is writeback truly needed, or is `NO_WRITEBACK` enough?
- Is the information useful beyond the current chat window?
- Is there evidence or explicit user confirmation?
- Are secrets, tokens, credentials, private chat transcripts, and unnecessary
  personal information excluded?
- Is the writeback type correct?
- Is the target file correct?
- Does this require user approval?
- Could this pollute memory with one-time speculation?
- Could this pollute the decision log with an unapproved or temporary idea?
- Is the update small enough to preserve state without copying noise?
- Will future GPT windows understand what changed and why?
