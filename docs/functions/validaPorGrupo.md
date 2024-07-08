# Validação por grupo

> Nesta sessão iremos utilizar uma função para realizar a validação se um determinado usuário pertence a um grupo.

Estaremos nos baseando na validação de usuário administrador presente no displayFields do processo **Req.Solicitação - Abertura Vaga** para a construção desse exemplo.

## Definição da função:

```
/* Valida usuário em um grupo */
function valida_usuario_grupo(idUsuario,cGrupo) {
	var erro = 0;
	var msg = "";

	let constraints_colleagueGroup = [];

	constraints_colleagueGroup.push(DatasetFactory.createConstraint("colleagueId", idUsuario, null, ConstraintType.MUST));

	var dataset_colleagueGroup = DatasetFactory.getDataset ("colleagueGroup", null, constraints_colleagueGroup, null);

	if (dataset_colleagueGroup != null && dataset_colleagueGroup.values.length > 0) {
		for (var i = 0; i < dataset_colleagueGroup.values.length; i ++) {
			if (dataset_colleagueGroup.getValue(i, "colleagueGroupPK.colleagueId") == idUsuario && dataset_colleagueGroup.getValue(i, "colleagueGroupPK.groupId") == cGrupo) {
				erro = 0;
				break;
			} else {
				erro = erro + 1;
			}
		}
	}
	if (erro == 0) {
		msg = "OK";
	} else {
		msg = "ERRO";
	}

	log.info("RETURN valida_usuario_rh: " + msg);
	return erro;
}
```

## Utilização:

### 1. Identificamos o grupo em questão:

```
FLUIG-ADMINISTRADORES
```

### 2. E inserimos o usuário, seguido pelo grupo nos parâmetros da função:

```
  var user = getValue("WKUser");
  valida_usuario_grupo(user, "FLUIG-ADMINISTRADORES");
```

### 3. Validação

Quando a função é executada sem nenhum erro, ela retorna 0, o que for diferente é um erro:

```
  if (valida_usuario_grupo(user, "FLUIG-ADMINISTRADORES") == 0) {
      form.setVisibleById("div_atribuicoes", true);
  }
```

> No código acima: Se o usuário pertence ao grupo de administradores, exibimos a divisão de atribuições.
