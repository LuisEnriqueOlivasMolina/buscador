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
		#datos	{border:1px solid #ccc;padding:10px;}
		#datos tr:nth-child(even) {background:#ccc;}
		#datos td {padding:5px;}
	</style>
</head>

<body>
	<h1>Buscar en el contenido de una tabla</h1>
	<form>
		Cadena a buscar <input id="searchTerm" type="text" onkeyup="doSearch()" />
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
				<td>3</td><td>pedro</td><td>Astorga</td><td>M</td><td>25</td>
			</tr>
			<tr>
				<td>4</td><td>Maria</td><td>Valdes</td><td>F</td><td>56</td>
			</tr>
		</table>
	</p>
</body>
</html>
