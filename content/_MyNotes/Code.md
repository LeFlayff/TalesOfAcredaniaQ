Git:
```bash
https://ghp_XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX@github.com/ithinkwong/linked-blog-starter-md.git
```

https://deepwiki.com/quartz-community/v5/2.3-theme-and-styling

Tags hinzufügen:
Get-ChildItem "C:\Users\furka\Desktop\Obsidian\TalesOfGit\content\INSERTHERE" -Filter *.md -Recurse | ForEach-Object {
    $content = Get-Content $_.FullName -Raw

    if ($content -notmatch '(?i)(?<!\w)#INSERTHERE\b') {
        Add-Content -Path $_.FullName -Value "`r`n`r`n#INSERTHERE"
        Write-Host "Tag hinzugefügt:" $_.FullName
    }
    else {
        Write-Host "Bereits vorhanden:" $_.FullName
    }
}

**Sync:**
npx quartz sync
