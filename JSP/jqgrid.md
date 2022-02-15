## 기본 함수 정리
- 선택한 행 rowid 가져오기
```
$('#그리드 아이디').jqGrid('getGridParam','selrow')
```
- 그리드 새로고침
```
$('#그리드 아이디').trigger('reloadGrid')
```
- 그리드 원하는 행 선택
```
$('#그리드 아이디').setSelection('원하는 rowid',true)
```
- 그리드 원하는 행 삭제
```
$('#그리드 아이디').delRowData('원하는 rowid')
```
- 그리드 비우기
```
$('#그리드 아이디').jqGrid('clearGridData')
```










