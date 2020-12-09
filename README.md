# xURL 

### _a `sed`-based URL-string encoder / decoder_

__________________

## Description

__xURL__ is a sed-based CLI tool which helps converting your string's special characters into their URL compatible representations. 

As a one-shot replacement of a potentially long `sed` command, these scripts will take in your input stream and output an encoded or decoded version of it.

It is `base64` compatible, and there are separate scripts to facilitate that type of usage (`xurlbase64enc` and `xurlbase64dec`). This is especially useful to simplify URL-safe, `base64` encoded payloads, such as SAML requests and responses.

___________________

## Installation

_Installer: TBA_

Clone this repo to your local machine and symlink the binaries to your `/usr/bin` folder:

```
git clone https://github.com/zalgonoise/xurl \
&& sudo ln -s -f $(pwd)/xurl/src/bin/* /usr/bin/.
```


___________________

## Contents

- `xurlenc`: Encodes input stream into an URL-safe string.
- `xurldec`: Decodes URL-safe input stream into a normal string (with special characters if present).
- `xurlbase64enc`: Basically `base64 --wrap=0 | xurlenc`.
- `xurlbase64enc`: Basically `xurldec | base64 -d`.

___________________

## Character Replacements

Character | URL-safe representation
:--------:|:-----------------------:
` `|`%20`
`!`|`%21`
`"`|`%22`
`#`|`%23`
`$`|`%24`
`%`|`%25`
`&`|`%26`
`'`|`%27`
`(`|`%28`
`)`|`%29`
`*`|`%2A`
`+`|`%2B`
`,`|`%2C`
`-`|`%2D`
`.`|`%2E`
`/`|`%2F`
`:`|`%3A`
`;`|`%3B`
`<`|`%3C`
`=`|`%3D`
`>`|`%3E`
`?`|`%3F`
`@`|`%40`
`[`|`%5B`
`\`|`%5C`
`]`|`%5D`
`^`|`%5E`
`\`|`%5F`
<code>\`</code>|`%60`
`{`|`%7B`
`|`|`%7C`
`}`|`%7D`
`~`|`%7E`