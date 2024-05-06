# devdilettante-backups
devdilettante.com mastodon backups
## 2024-05-05 generate an array

```bash
jq '[.orderedItems | .[]  | {id: .object.id? | select (. !=null), content: .object.content? | select(. != null)}]' outbox.json  > array_filtered_id_content.json
```

## 2024-05-05 getting the contents of the toots from the archive using jq
```bash
cd 2024-05-04-devdilettante-com-archive-20240505032936-7d3110aafe1a03f80e3db147600edd38/
jq '.orderedItems | .[]  | {id: .object.id? | select (. !=null), content: .object.content? | select(. != null)}' outbox.json > filtered_id_content.json
```
