<h1 align="center">YJDict - A Japanese Dictionary</h1>
<p align="center">
    <a href="https://www.rust-lang.org/" alt="Made In">
        <img src="https://img.shields.io/badge/SCRAPED WITH-Rust-red?style=for-the-badge&logo=rust&logoColor=red" /></a>
    <a href="https://github.com/yxl-prz/YJDict/releases/latest/download/yjdict.json" alt="Download">
        <img src="https://img.shields.io/badge/DOWNLOAD-RAW-yellow?style=for-the-badge" /></a>
    <a href="https://github.com/yxl-prz/YJDict/graphs/contributors" alt="Version">
        <img src="https://img.shields.io/github/contributors/yxl-prz/YJDict?style=for-the-badge" /></a>
</p>

# Structures
## [Rust](#rs-rust) | [Go](#rust--go)
## `.rs`: **Rust**
```rs
struct YJDict {
    id: i32,
    expression: String,
    reading: String,
    definitions: YJDictDefinitions,
    pitch: Option<Vec<YJDictPitch>>,
}

struct YJDictDefinitions {
    en: Vec<String>,
    es: Vec<String>,
    fr: Vec<String>,
    nl: Vec<String>,
    hu: Vec<String>,
    ru: Vec<String>,
    sv: Vec<String>,
    de: Vec<String>,
}

struct YJDictPitch {
    postion: i8,
    notation: Vec<char>,
}
```
## `.go`: **Go**
```go
type YJDict struct {
	ID          int32             `json:"id"`
	Expression  string            `json:"expression"`
	Reading     string            `json:"reading"`
	Definitions YJDictDefinitions `json:"definitions"`
	Pitch       *YJDictPitch      `json:"pitch"`
}

type YJDictDefinitions struct {
	EN []string `json:"en"`
	ES []string `json:"es"`
	FR []string `json:"fr"`
	NL []string `json:"nl"`
	HU []string `json:"hu"`
	RU []string `json:"ru"`
	SV []string `json:"sv"`
	DE []string `json:"de"`
}

type YJDictPitch struct {
	Position int8   `json:"position"`
	Notation []byte `json:"notation"`
}
```

# Credits
- ⭐ **JMDict** [[link](https://www.edrdg.org/jmdict/edict_doc.html)]: Majority of the definitions were taken from different variations of the **JMDict** dictionary.
- ⭐ **Kanjium** [[link](https://github.com/mifunetoshiro/kanjium)]: The pitch accent information was taken from **Kanjium**.