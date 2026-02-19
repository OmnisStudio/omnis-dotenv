# omnis-dotenv

Reads a local .env file on startup and sets env vars matching its contents. This can be a useful means of importing secrets without embedding them in your code.

You might use a .env file in your dev environment, and use some other mechanism to set the env vars in your production environment (e.g. docker run arguments).


# Installation

This repo contains a JSON export of an omnis library - 'dotenv'. It can be *imported* into Omnis to build an Omnis Library.


# Usage

On startup, this will look for a `.env` file in the root of your Omnis installation's *writable files* area.
If found, it will set **Environment Variables** according to the content of this file.

The `.env` file's content should be made up of multiple lines defining environment vars:

```
<Var Name> = <Var Value>
```

- You can include white space around the variable name and/or value.
- You can (but do not need to) quote values with double-quotes.
- You can create comment lines using a `#` as the first non-white-space character of a line.

Using Omnis code, you can then obtain these values using the `getenv()` function.

## Important!
If they contain secrets, treat your *.env* files with utmost care, **do not commit them** to any source control.
