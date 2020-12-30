I decided to create this extension in late 2020 because JetBrains Darcula is my favourite color theme out there. However, I could not find any decent implementation of it for VS Code.

Supported languages:

- C#
- JavaScript
- TypeScript
- HTML
- CSS
- JSON
- XML
- YAML

This color theme natively supports semantic highlighting for all languages mentioned above that support this feature.

In order to implement a support for a given language I first extract all classifiation type defined in the TextMate syntax file. Then I pull all the scopes into the color theme and give them red foreground. Then I try to get every type to display in the editor and find out which color does it get in the JetBrains editor (e.g. Rider, IntelliJ IDEA, etc.). Finally I define the right style for every classification type. I do this until all the classification types are given the right style.

Unfortunately I am not able to simulate all classification scopes because some of them are really obscure. I keep these under "unknown" block in the color theme file so that thay will immediately draw attention if someone is lucky enough to stumble upon them in the future. If that is your case, please file an issue with an instruction how to reproduce it and I will correct the color.

There are some minor differences between my implementation and that by JetBrains. For example, string escape characters are orange in e.g. C# but green in YAML. In my implementation they are always orange. Type parameters are green-like in TypeScript but grey in C#. In my implementation they are always green-like.

I am currently not planning to support any other languages because I do not use them.
