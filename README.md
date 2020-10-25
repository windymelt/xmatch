# xmatch

`xmatch` is command line tool which extracts valiables from XML, using pattern file (still alpha)

## Prerequistes

- [Roswell](https://github.com/roswell/roswell)

## Usage

Output format is still developing.

```shell
$ ./xmatch.ros -e PATTERNFILE SOURCEFILE
```

### Build (optional)

```shell
$ ros build xmatch.ros
```

## Feature

- text node string pattern match `<string var="variable-name" />`

## Source file example

```xml
<?xml version="1.0" encoding="UTF-8"?>
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="jp" lang="jp">
<body>
    <h1>Some title</h1>
    <article>
        <h2>Some article title</h2>
        <p class="first active">foo bar buzz piyo</p>
        <p class="second">hogehogefugafuga</p>
    </article>
</body>
</html>
```

## Pattern file example

```xml
<?xml version="1.0" encoding="UTF-8"?>
<pattern>
    <p class="second"><string var="variable-name" /></p>
</pattern>
```

This pattern file extracts `hogehogefugafuga` from source file as `variable-name`.