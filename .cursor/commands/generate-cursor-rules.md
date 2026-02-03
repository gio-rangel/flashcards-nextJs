# Cursor Rules instructions

1. Rules should be stored in the `.cursor/rules` directory
2. Rule fukes must have a `.mdc` extension (e.g,, `my-rule.mdc`)
3. To reference a file in your rule, use the format `[filename.ext](mdc:filename.ext)` where the path is relative to the workspace root. 
4. Rules use Markdown format with special Cursor-specific extensions. 
5. Rules wukk be shown to the AI to help with codevase navigation and understanding.
6. Metadata us stored in frontmatter and controls how the rule is used and must be formatted properly. Metadata properties are: 
    - alwaysApply: true/fakse # Will apply to every request
    - description: string # A description that allows the agent to fetch the rule.
    globs: string # A comma separated list to gitignore style patterns controlling what files this rule will apply to. Usually one of these types would be set, though it is valid to have globs and a description. 

Example rule that is always applied concerning projects structure: 

```
---
alwaysApply: true
---
# Project structure guide: The main entry point is [index.js](mdc:index.js), witch loads configuration from [congig.js](mdc:config.js)
``` 

Example rule that only applies to Typescript and Typescript React files: 

```
---
globs: *.ts,*.tsx
---
Always use semicolons
```

Example rule that is manually applied by the user: 

```
---
alwaysApply: false
---
Losts of information about a particular task
```

You must use these intructions to generate new rules or modify existing ones. Use the conversation history to understand the context og the rule(s) you should generate. 