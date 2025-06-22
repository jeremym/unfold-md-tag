# unfold-md

**unfold-md** is a custom, recursive markdown extension that introduces an expressive way to define expandable or modal-style content blocks using simple tag-like syntax.

People won't read everything you write, but you can make it easier to skim and consume.

Ever find yourself writing messages or documentation that are overloaded with context, side notes, or background explanations. Often, these details are helpful, but not essential to the main point. Traditional markdown doesn’t offer a clean way to fold or hide that extra content.

**unfold-md** provides a lightweight syntax for embedding expandable content directly in markdown, allowing writers to separate core ideas from optional context without disrupting flow.

## Example

```md
[[What is unfold-md?]]{{{
  unfold-md is a way to create expandable content blocks in markdown.

  You can even nest them:

  [[What about nesting?]]{{{
    This content is inside a nested block.
  }}}
}}}
```

#### Example Rendering (Conceptual)

```markdown
## Conceptual Rendering

When parsed by a renderer that supports `unfold-md`, the above syntax might display like this:

> **What is unfold-md?**  
> (Clicking this would expand a section below containing:)  
> 
> unfold-md is a way to create expandable content blocks in markdown.
>
> **What about nesting?**  
> (Clicking this would expand again to show:)  
> This content is inside a nested block.

This functionality is similar to collapsible sections, modals, or tooltips (and may render that way depending on the parser) — but written entirely in markdown using `[[label]]{{{content}}}` syntax.
```

## Syntax

- `[[Label]]` — defines a clickable text or anchor  
- `{{{Content}}}` — defines the hidden content to be shown on interaction  
- The pattern can be **nested recursively**, allowing deeply structured content  
- Only custom parsers or compatible frontends will render this properly  

## Use Cases

- Interactive or nested documentation  
- Self-revealing educational content  
- In-place glossary terms with explanations (what does xyz mean → think of a wiki article where you wouldn't need to leave the page you're visiting, even allowing you to go a few pages deep)  
- Markdown-based slide decks with expanding notes  
- Interactive wikis or expandable tables of content  
