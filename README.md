# **renovate config**

個人用のrenovateの設定を一括管理するためのアレ

[npm](https://www.npmjs.com/package/@hpprc/renovate-config)

## config list


### default

standard config for active repositories

```json

{
    "default": {
      "extends": [
        "config:base"
      ]
    },
}

```

### maintenance

- automerge for devDependencies
- skip ci for Netlify build
  - Netlify ignore any commits whose commit message starts with "[skip ci]"
  - this config force Netlify to avoid triggering builds

```json
{
    "maintenance": {
        "extends": [
            "config:base"
        ],
        "packageRules": [
            {
            "depTypeList": [
                "devDependencies"
            ],
            "automerge": true,
            "commitMessagePrefix": "[skip ci]"
            }
        ]
    }
}
```