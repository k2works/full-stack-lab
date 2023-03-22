# full-stack-lab
フルスタック開発教育支援ツール

## install

```bash
npm install @k2works/full-stack-lab
```

## usage

```js
import { render } from "full-stack-lab";
const contents = `
## 機能名
## 仕様
## TODOリスト
`;

const uml = `
abstract class AbstractList
abstract AbstractCollection
interface List
interface Collection
List <|-- AbstractList
Collection <|-- AbstractCollection
Collection <|- List
AbstractCollection <|- AbstractList
AbstractList <|-- ArrayList
class ArrayList {
  Object[] elementData
  size()
}
enum TimeUnit {
  DAYS
  HOURS
  MINUTES
}
annotation SuppressWarnings
`;

const erd = `
' hide the spot
hide circle
' avoid problems with angled crows feet
skinparam linetype ortho
entity "Entity01" as e01 {
  *e1_id : number <<generated>>
  --
  *name : text
  description : text
}
entity "Entity02" as e02 {
  *e2_id : number <<generated>>
  --
  *e1_id : number <<FK>>
  other_details : text
}
entity "Entity03" as e03 {
  *e3_id : number <<generated>>
  --
  e1_id : number <<FK>>
  other_details : text
}
e01 ||..o{ e02
e01 |o..o{ e03
`;
render({ contents, uml, erd });
```

## license

MIT. Copyright (c) [k2works](http://feross.org).