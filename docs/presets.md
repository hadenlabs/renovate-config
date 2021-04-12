## Available presets

### autoMergePin

```json
{
  "pin": {
    "automerge": true
  }
}
```

### autoMergeTypesMinor

```json
{
  "packageRules": [
    {
      "matchPackagePatterns": ["^@types/"],
      "automerge": true,
      "major": {
        "automerge": false
      }
    }
  ]
}
```

### groupJest

Grouping jest monorepo packages and ts-jest.

```json
{
  "packageRules": [
    {
      "groupName": "jest",
      "matchSourceUrlPrefixes": [
        "https://github.com/facebook/jest",
        "https://github.com/kulshekhar/ts-jest"
      ]
    }
  ]
}
```

### groupLinters

Grouping lint-related packages for JavaScript and TypeScript. Adding prettier and typescript-eslint packages to the [`packages:linters` preset](https://docs.renovatebot.com/presets-packages/#packageslinters).

```json
{
  "packageRules": [
    {
      "groupName": "linters",
      "extends": ["packages:linters"],
      "matchPackageNames": ["prettier"],
      "matchPackagePatterns": ["^@typescript-eslint/"]
    }
  ]
}
```

### schedule

```json
{
  "extends": [":timezone(America/Lima)"],
  "schedule": ["after 10:30 before 18:00 every weekday except after 13:00 before 14:00"]
}
```

This config is heavily based on our business hours in Hadenlabs. So if this is not a good fit for you, please exclude as follows:

```json
{
  "ignorePresets": ["github>hadenlabs/renovate-config:schedule"]
}
```

or extend the [Schedule Presets](https://docs.renovatebot.com/presets-schedule/).
