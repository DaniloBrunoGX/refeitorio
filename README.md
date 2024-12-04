<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>New Aluno</title>
    <link rel="stylesheet" href="/css/bootstrap.css">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
</head>
<body>
<h2>Cadastro de Alunos</h2>
<form method="POST" enctype="multipart/form-data">
    {% csrf_token %}
    {{ form }}
    <input type="submit" value="Inserir">
</form>
<h1>Mostrar Alunos</h1>

    <table class="table table-activate">
        <thead>
        <td>Foto</td>
        <td>Nome</td>
        <td>Matricula</td>
        <td>Editar</td>
        <td>Excluir</td>
        </thead>
        <tbody>
        {% for aluno in alunos %}

    <tr>
        <td><img src="{{aluno.foto_url}}" alt="Foto"></td>
        <td>{{aluno.nome_aluno}}</td>
        <td>{{aluno.matricula_aluno}}</td>
        <td><a href="{% url 'editar_aluno' aluno.id_aluno %}" class="btn btn-warning">Editar</a></td>
        <td><a href="{% url 'excluir_aluno' aluno.id_aluno %}" class="btn btn-danger">Excluir</a></td>
    </tr>
        {% endfor %}
    </tbody>
    </table>

</body>
</html>
