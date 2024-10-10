# Publish PowerShell GitHub Action

A GitHub Action to publish a PowerShell module or script to GitHub Packages, a NuGet repository, or the PowerShell Gallery.

Forked from https://github.com/natescherer/publish-powershell-action for my own usage and learning. 

**NOT ACTIVELY TESTED or developed**: Recomend using https://github.com/natescherer/publish-powershell-action instead if you want a tested or easy to use version.

## Usage

```yaml
    steps:
      - name: Publish PowerShell Module
        uses: vertigo-one/publish-powershell-action@main
        with:
          token: ${{ secrets.GITHUB_TOKEN }}
          target: packages
          path: src
```

```yaml
    steps:
      - name: Publish PowerShell Module
        uses: vertigo-one/publish-powershell-action@main
        with:
          token: ${{ secrets.NUGET_TOKEN }}
          target: nuget
          path: src
```

```yaml
    steps:
      - name: Publish PowerShell Module
        uses: vertigo-one/publish-powershell-action@main
        with:
          token: ${{ secrets.GALLERY_API_KEY }}
          target: gallery
          path: src
```

### Inputs

<!--(inputs-start)-->

| Name  | Required | Default | Description |
| :---: | :------: | :-----: | ----------- |
| `token` | true |  | Token to authenticate. |
| `target` | true |  | Set to `packages` for GitHub Packages, `gallery` for the PowerShell Gallery, or `nuget` for a NuGet repository. |
| `path` | true |  | Path to publish relative to the root of the project. Can either be a .psd1 file, a .ps1 file, or a directory. If a directory, the action will search for a .psd1 file in the root. If none are found, it will then <br>search for a .ps1 file in the root. |
| `nugetUrl` | false |  | Url to use with NuGet target. Should be a NuGet v2 or v3 endpoint. |

<!--(inputs-end)-->


## License

This project is licensed under The MIT License - see [LICENSE](LICENSE) for details.

