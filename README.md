# k8splugins

Este procedimento lhe ajudará a instalar plugins para o *kubectl* utilizando o projeto open source **Krew**. **Mas o que são plugins? Desde a versão 1.12, kubectl inclui um mecanismo que permite estender o CLI com comandos personalizados para aumenta a produtividade e facilitar o uso de algumas ferramentas.**

**Pré-requisitos instalados:**
- [x] git
- [x] kubectl
- [x] um cluster k8s configurado, no meu caso há uma no **Oracle Cloud (OKE)**


**Vamos aos passos:**

1. Abra seu Terminal

2. Execute

```
(
  set -x; cd "$(mktemp -d)" &&
  curl -fsSLO "https://github.com/kubernetes-sigs/krew/releases/latest/download/krew.tar.gz" &&
  tar zxvf krew.tar.gz &&
  KREW=./krew-"$(uname | tr '[:upper:]' '[:lower:]')_$(uname -m | sed -e 's/x86_64/amd64/' -e 's/arm.*$/arm/')" &&
  "$KREW" install krew
)
```

3. Feita a isntalação execute:
``` 
export PATH="${PATH}:${HOME}/.krew/bin"
``` 

4. Reinicie seu shell

```
<ALT> + <F2>, r, <Enter>
```

5. Para testar a instalação, no terminal digite

<table>
    <tbody>
        <tr>
        <th><img align="left" width="600" src="https://objectstorage.us-ashburn-1.oraclecloud.com/n/idsvh8rxij5e/b/imagens_git/o/Captura%20de%20tela%20de%202020-12-18%2022-28-20.png"/></th>
        </tr>
    </tbody>
</table>

<br>
Feito!!!
<br>
Agora à diversão:

<br>

**Para listar plugin disponíveis para instalação:**

```
$ kubectl krew search
```
<table>
    <tbody>
        <tr>
        <th><img align="left" width="600" src="https://objectstorage.us-ashburn-1.oraclecloud.com/p/X0mrMNZTQ-Se8xnW7QO0SZDRYEnDxJ6aauRkvKANIXVMlGC__02beJb5LwlOVrsx/n/idsvh8rxij5e/b/imagens_git/o/Captura%20de%20tela%20de%202020-12-18%2023-39-31.png"/></th>
        </tr>
    </tbody>
</table>


**Para instalar um plugin disponível:**

```
$ kubectl krew install <nomedoplugin>
```

<table>
    <tbody>
        <tr>
        <th><img align="left" width="600" src="https://objectstorage.us-ashburn-1.oraclecloud.com/p/hh-pa5unBVtdxksF-53LICHhLQnkWAAtoqEqbVHQNk5Icy9_AIqUdwN0j_tjxkIn/n/idsvh8rxij5e/b/imagens_git/o/Captura%20de%20tela%20de%202020-12-18%2023-40-05.png"/></th>
        </tr>
    </tbody>
</table>


***Quais meus plugins prediletos?***

- Tree
- Debug
- Popeye
- kyverno
- MinIO
- kubesec-scan (https://kubesec.io/)
- ca-cert








