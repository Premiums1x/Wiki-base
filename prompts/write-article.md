You are a wiki author writing a comprehensive article about a concept.

Concept: {{.ConceptName}}
Sources: {{.Sources}}
Related concepts: {{.RelatedList}}

{{if .ExistingArticle}}
## Existing article (update/expand):
{{.ExistingArticle}}
{{end}}

{{if .SourceContext}}
## Relevant source material:
{{.SourceContext}}
{{end}}

{{if .Learnings}}
## Learnings from previous compilations (follow these):
{{.Learnings}}
{{end}}

Write a structured wiki article with:

## Definition
Clear, precise definition of the concept.

## How it works
Technical explanation with appropriate depth.

## Variants
Known variants, implementations, or alternatives.

## Trade-offs
Key trade-offs, limitations, or considerations.

## See also
List related concepts as [[wikilinks]]:
{{range .RelatedConcepts}}- [[{{.}}]]
{{end}}

CRITICAL INSTRUCTION FOR RELATION EXTRACTION:
You MUST integrate the related concepts from the Related concepts list inline in your article's text (specifically in the Definition, How it works, Variants, or Trade-offs sections). When mentioning a related concept in the text:
1. Wrap it in double brackets [[wikilink]] (using its kebab-case name as listed in the Related concepts list).
2. Explicitly state the relationship in the same sentence or paragraph using relationship action words or synonyms such as:
   - "extends", "builds on" (for RelExtends)
   - "implements", "is an implementation of" (for RelImplements)
   - "optimizes", "improves upon", "faster than" (for RelOptimizes)
   - "depends on", "requires", "prerequisite of" (for RelPrerequisiteOf)
   - "trades off with", "at the cost of" (for RelTradesOff)
   - "contradicts", "conflicts with" (for RelContradicts)
Do not just list them in the "See also" section; actively explain how they relate in the text using these exact relationship keywords.

Do NOT include YAML frontmatter — it will be added automatically.

At the very end of your response, add exactly one line assessing your confidence:
Confidence: high, medium, or low

Keep under {{.MaxTokens}} tokens. Be precise and factual.
