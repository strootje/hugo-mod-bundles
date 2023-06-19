# Bundles

## Usage

This module automaticaly pulls `scss` and `ts` files from the assets directory.
Use the following naming scheme's:
- assets/styles/bundle/\_*\_<head/body>_<start/end>.scss
- assets/scripts/bundle/\_*\_<head/body>_<start/end>.ts
- layouts/partials/bundle/\_\<key\>\_<head/body>_<start/end>.html

For partials you have to add a `key` in the list `[[params.mod.bundles]]`.
```toml
[[params.mod.bundles]]
key = "testing"

# Will check
# - partial "bundle/_testing_head_end" .
# - partial "bundle/_testing_body_start" .
# - partial "bundle/_testing_body_end" .
```

```html
<!DOCTYPE html>
<html lang="en">
	<head>
      <!-- ... -->
		{{- partial "bundle/head/end" . -}}
	</head>
	<body>
		{{- partial "bundle/body/start" . -}}

      <!-- ... -->

		{{- partial "bundle/body/end" . -}}
	</body>
</html>
```

## Installation
```bash
$ hugo mod get -u git.strooweb.nl/strooware/hugo-mod-bundles
```
