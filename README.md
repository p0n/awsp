# awsp

Simple switcher for AWS CLI profiles inspired by [johnnyopao/awsp](https://github.com/johnnyopao/awsp).

This tool is simple enough to set the selected profile to AWS_PROFILE environment variable, but added some features I wanted.

- Display the current profile.
- Display the profile configuration during selection
- Deselect the current profile.

## Prereqs

- [fzf](https://github.com/junegunn/fzf)
- zsh (work on bash as well?)
- [GNU sed](https://www.gnu.org/software/sed/) (Mac only)

## Setup

Clone this repository and import ```.zshrc.func.awsp``` to your .zshrc.

```sh
if [ -f <path-to-cloned-repo>/.zshrc.func.awsp ]; then
    source <path-to-cloned-repo>/.zshrc.func.awsp
fi
```

## Usage

```sh
awsp
```

Use up/down keys to select a profile. Incremental filtering is also supported. Select "~N/A" to deselect the current profile.

```text
> 
  6/6 
  CURRENT PROFILE=N/A
  dev-admin
> dev-readonly
  lab-admin
  master
  security
  ~N/A

╭──────────────────────────────────────────────────────────────────────╮
│      Name                   Value           Type    Location         │
│      ----                   -----           ----    --------         │
│   profile            dev-readonly         manual    --profile        │
│access_key    ****************ZQhV            sso                     │
│secret_key    ****************6X39            sso                     │
│    region               us-west-2    config-file    ~/.aws/config    │
╰──────────────────────────────────────────────────────────────────────╯
```
