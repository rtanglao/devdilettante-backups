# devdilettante-backups
devdilettante.com mastodon backups

## 2024-10-14 Browse my backup using datasette
* [Browse my October 14, 2024 mastodon backup using datasette](https://lite.datasette.io/?json=https%3A%2F%2Fraw.githubusercontent.com%2Frtanglao%2Fdevdilettante-backups%2Fmain%2F2024-10-14-devdilettante-com-archive-20241014185358-e0ea2667cabb23c111a6001efa19216e%2Foutbox.json#/data?sql=select+*+from+outbox) <-- not as useful as it seems since the backup doesn't have the text of the boosted toots.It does have the URL of boosted toots but not the content. The content does appear for toots you created yourself of course!
## 2024-05-05 Search the array of content and id with datasette lite
* [super long url that loads array_filtered_id_content.json into lite.datasette.io](https://lite.datasette.io/?json=https%3A%2F%2Fraw.githubusercontent.com%2Frtanglao%2Fdevdilettante-backups%2Fmain%2F2024-05-04-devdilettante-com-archive-20240505032936-7d3110aafe1a03f80e3db147600edd38%2Farray_filtered_id_content.json#/data/array_filtered_id_content)

## 2024-05-05 generate an array

```bash
jq '[.orderedItems | .[]  | {id: .object.id? | select (. !=null), content: .object.content? | select(. != null)}]' outbox.json  > array_filtered_id_content.json
```

## 2024-05-05 getting the contents of the toots from the archive using jq
```bash
cd 2024-05-04-devdilettante-com-archive-20240505032936-7d3110aafe1a03f80e3db147600edd38/
jq '.orderedItems | .[]  | {id: .object.id? | select (. !=null), content: .object.content? | select(. != null)}' outbox.json > filtered_id_content.json
```
