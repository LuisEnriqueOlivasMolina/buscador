<!DOCTYPE html>
<html lang="es">
<head>
	<title>Buscar en el contenido de una tabla</title>
	<script language="javascript">
		function doSearch()
		{
			var tableReg = document.getElementById('datos');
			var searchText = document.getElementById('searchTerm').value.toLowerCase();
			var cellsOfRow="";
			var found=false;
			var compareWith="";

			for (var i = 1; i < tableReg.rows.length; i++)
			{
				cellsOfRow = tableReg.rows[i].getElementsByTagName('td');
				found = false;

				for (var j = 0; j < cellsOfRow.length && !found; j++)
				{
					compareWith = cellsOfRow[j].innerHTML.toLowerCase();

					if (searchText.length == 0 || (compareWith.indexOf(searchText) > -1))
					{
						found = true;
					}
				}
				if(found)
				{
					tableReg.rows[i].style.display = '';
				} else {

					tableReg.rows[i].style.display = 'none';
				}
			}
		}
	</script>

	<style>
	#datos	{border:1px solid #ccc;padding:20px;}
	#datos tr:nth-child(even) {background:#ccc;}
	#datos td {padding:20px;}
		#datos {
position: absolute;
top: 130px;
left: 50%;
margin-left: -181px;
width: 361px;
height: 320px;
text-align:left;
}
	</style>
</head>

<body>
	<h1 align="center"> Buscardor planilla</h1>
	<form align="center">
		Datos de busqueda<input id="searchTerm" type="text" onkeyup="doSearch()" />
	</form>
	<p>
		<table id="datos">
			<tr>
				<th>id</th><th>Nombre</th><th>Apellidos</th><th>Género</th><th>Edad</th>
			</tr>
			<tr>
				<td>1</td><td>Luis</td><td>Olivas</td><td>M</td><td>30</td>
			</tr>
			<tr>
				<td>2</td><td>Jose</td><td>Vazquez</td><td>M</td><td>31</td>
			</tr>
			<tr>
				<td>3</td><td>Pedro</td><td>Astorga</td><td>M</td><td>25</td>
			</tr>
			<tr>
				<td>4</td><td>Maria</td><td>Valdes</td><td>F</td><td>56</td>
			</tr>
			<tr>
				<td>1</td><td>Francisco</td><td>Perez</td><td>M</td><td>30</td>
			</tr>
			<tr>
				<td>1</td><td>Rafael</td><td>Martinez</td><td>M</td><td>30</td>
			</tr>
			<tr>
				<td>1</td><td>Josue</td><td>Estarda</td><td>M</td><td>30</td>
			</tr>
			<tr>
				<td>1</td><td>Javier</td><td>Roa</td><td>M</td><td>30</td>
			</tr>
		</table>
	</p>
</body>
</html>
