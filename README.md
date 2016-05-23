<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		#table{
			margin:0 auto;
		}
		#container{
			margin:0 auto;
			border:solid 2px pink;
		}
		input{
			width:200px;
			margin:0 auto;
			display:block;
		}
	</style>
</head>
<body>
<div id="container">
	<table border="1" width="50%" id="table">
		<tr align="center">
			<th>学号</td>
			<th>姓名</td>
			<th>操作</td>
		</tr>
		<tr>
			<td>xh001</td>
			<td>王小明</td>
			<td><a href="#" onclick="del(this)">删除</a></td>
		</tr>
	</table>
	<input type="button" value="增加" onclick="add()"/>
</div>
	<script src="./scripts/addLoadEvent.js"></script>
	<script type="text/javascript">
	 function add(){
	 	var tbody=document.getElementById('table').lastChild;
	 	var tr=document.createElement('tr');
	 	var td=document.createElement('td');
	 	td.innerHTML="<input type='text'/>";
	 	tr.appendChild(td);
	 	td=document.createElement('td');
	 	td.innerHTML="<input type='text'/>";
	 	tr.appendChild(td);
	 	td=document.createElement('td');
	 	td.innerHTML="<a href='#' onclick='del(this)'>删除</a>";
	 	tr.appendChild(td);
	 	tbody.appendChild(tr);
	 	Highlight();
	 }
	 function Highlight(){	
		trs = document.getElementsByTagName('tr');  
		for(var i =1;i<trs.length;i++){
			trs[i].onmouseover = function(){
				this.style.backgroundColor ="pink";
			} 
			trs[i].onmouseout = function(){
				this.style.backgroundColor ="#fff";
			} 
		}  
	 }
	 function del(obj){
	 	var table=document.getElementById('table').lastChild;
	 	var tr=obj.parentNode.parentNode;
	 	table.removeChild(tr);	 	
	 }
	 window.onload=function()
	 {
	 Hightlight();
	 }
	</script>
</body>
</html>
