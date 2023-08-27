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
pub struct Item {
    pub expression: String,
    pub reading: String,
    pub definitions: HashMap<String, Vec<String>>,
    pub pitches: Option<Vec<ItemPitch>>,
    pub frequency: Option<u32>,
}

pub struct ItemPitch {
    drop: i16,
    notation: Vec<char>,
}

```
## `.go`: **Go**
```go
type YJDict struct {
	ID          int32                 `json:"id"`
	Expression  string                `json:"expression"`
	Reading     string                `json:"reading"`
	Definitions map[string]([]string) `json:"definitions"`
	Pitch       *YJDictPitch          `json:"pitch"`
}

type YJDictPitch struct {
	Position int8   `json:"position"`
	Notation []byte `json:"notation"`
}
```

## `.sql`: **SQL**
```sql
CREATE TABLE Expressions(
    expression TEXT NOT NULL,
    reading TEXT DEFAULT NULL,
    definitions JSONB NOT NULL,
    pitches JSONB,
    frequency INTEGER DEFAULT NULL
);
```

# Credits
- ⭐ **JMDict** [[link](https://www.edrdg.org/jmdict/edict_doc.html)]: Majority of the definitions were taken from different variations of the **JMDict** dictionary.
- ⭐ **Kanjium** [[link](https://github.com/mifunetoshiro/kanjium)]: The pitch accent information was taken from **Kanjium**.
- ⭐ **Innocent Corpus** [[link](https://web.archive.org/web/20190309073023/https://forum.koohii.com/thread-9459.html#pid168613)]: The frequency of the expressions were taken from **Innocent Corpus**.