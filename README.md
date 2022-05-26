# figma-tokens-example-multi

This example illustrates how you can transform your tokens stored on Figma Tokens (with GitHub sync enabled) to be automatically transformed with token-transformer and Style Dictionary in a dark/light theme environment.

Change your tokens in `tokens.json` (either directly or with the Figma Tokens plugin in Figma). The GitHub action will automatically generate tokens to the `tokens/` directory that can then be read by Style Dictionary, which will output tokens to the format you defined in `build.js` - css variables will be generated in the `output` directory.


## customization

1. Update the "create-tokens.yml" file to indicate how the new sets should be constructed from single tokens.json to individual sets (colors.json, typography-x.json, theme.json, etc.).

Pay attention to the syntax of token transformer.

node token-transformer (source).json (output).json (set 1),(set 2),(etc.) (excluding set)
-> node token-transformer tokens.json tokens/theme.json global,colors,typography-one global

2. Update build.js to include which json files to convert to css files.
