# AntihAL project check sample

This tiny greeting program uses Python's standard library. Its requirements.txt is an intentionally unsafe test input for a dependency scanner. Leave it uninstalled.

| Declaration | Why it is included |
|---|---|
| python-dateutil-malicious 2.5.4 | Historical malicious release. [OSV advisory](https://osv.dev/vulnerability/MAL-2025-2992) |
| ultralytics 8.3.41 | Compromised release. [PyPA advisory](https://osv.dev/vulnerability/PYSEC-2024-154) |
| requests 9999.0.0 | Deliberately invented release to exercise registry checks |
| idna 3.10 | Published release for comparison |

## Test with GitHub

1. Create an empty public repository on GitHub.
2. Select **uploading an existing file** (or **Add file → Upload files**). Upload this folder's README.md, app.py and requirements.txt at the repository root. Commit them to the default branch.
3. Copy the repository's main URL. Open **Project checker → GitHub repository** in AntihAL, paste the URL and select **Check dependencies**.
4. Inspect each decision and download the evidence. The status for a removed release can reflect its absence from the registry. A registry outage can also produce a review decision.
