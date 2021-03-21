# Alternativas para instalación simple de k8s

Kubernetes es un software pensado para poner en producción aplicaciones más o menos complejas que se ejecutan sobre contenedores, garantizando su disponibilidad, escalabilidad y actualización sin interrupciones. En un entorno en producción no se instala kubernetes en un solo equipo (nodo), sino que creamos un cluster de nodos que permita garantizar el funcionamiento ininterrumpido de las aplicaciones incluso en el caso de que uno o varios de los nodos del cluster tengan algún tipo de incidencia.

Configurar y actualizar un cluster de kubernetes es una tarea compleja, pero existe la posibilidad de instalar de forma fácil un cluster de kubernetes compuesto por un solo nodo o un conjunto pequeño para algunos casos de uso, como en el caso de la instalación de un entorno de desarrollo o aprendizaje, que es precisamente la situación que tenemos en nuestro caso. Estas instalaciones de kubernetes no son adecuadas para entornos en producción, pero nos permiten utilizar kubernetes de forma sencilla, conocer los objetos y atacar la API sin tener que utilizar una instalación más compleja o costosa.

# minikube

![minikube-logo](https://raw.githubusercontent.com/kubernetes/minikube/master/images/logo/logo.png =100px)

minikube permite desplegar localmente un "cluster" de kubernetes con un solo nodo. minikube es un proyecto oficial de kubernetes y es probablemente la solución más adecuada para aprender a usar k8s, ya que es un proyecto maduro y muy sencillo de instalar. Los requisitos mínimos para instalar minikube en nuestro equipo son:

* 2 CPUs
* 2GiB de memoria
* 20GiB de espacio libre en disco
* Un sistema de virtualización o de contenedores instalado:
  * Docker
  * Hyperkit
  * Hyper-V
  * KVM
  * Parallels
  * Podman
  * VirtualBox
  * VMWare

Minikube instalará un nodo de kubernetes en el sistema de virtualización/contenedores que prefiramos, dependiendo el sistema adecuado del sistema operativo de nuestro equipo, tal como se muestra en [https://minikube.sigs.k8s.io/docs/drivers/](https://minikube.sigs.k8s.io/docs/drivers/).

Los detalles para la instalación local de minikube los explicamos en la siguiente sección, ya que va a ser el método recomendado para realizar este curso.

# kubeadm

![kubeadm-logo](https://raw.githubusercontent.com/kubernetes/kubeadm/master/logos/stacked/color/kubeadm-stacked-color.png =100px)

kubeadm es una solución más realista que minikube, ya que sí se instala un cluster de kubernetes con varios nodos. La instalación de kubeadm no es especialmente compleja, pero no está tan automatizada como minikube y necesita más recursos y tiempo para configurarlo. kubeadm es una opción muy interesante cuando queremos ver de forma detallada la diferencia entre lo que se ejecuta en el nodo controlador y en los nodos workers, que no se puede apreciar en minikube.

La instalación de kubeadm se realiza típicamente en varias máquinas virtuales o varias instancias de nube y dejamos un par de enlace para quienes estén más interesados en indagar en este software:

* [https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/)
* [https://www.josedomingo.org/pledin/2018/05/instalacion-de-kubernetes-con-kubeadm/](https://www.josedomingo.org/pledin/2018/05/instalacion-de-kubernetes-con-kubeadm/)

# kind

![kind-logo](https://d33wubrfki0l68.cloudfront.net/d0c94836ab5b896f29728f3c4798054539303799/9f948/logo/logo.png =100px)

kind (kubernetes in docker) es un proyecto oficial de kubernetes más reciente que los dos anteriores y que permite desplegar un cluster de kubernetes con varios nodos sobre docker. Es también muy interesante como opción de instalación local y de forma análoga al anterior, dejamos un par de enlaces para quienes estén interesados en probarlo:

* [https://kind.sigs.k8s.io/docs/user/quick-start/](https://kind.sigs.k8s.io/docs/user/quick-start/)
* [https://www.josedomingo.org/pledin/2021/02/kubernetes-con-kind/](https://www.josedomingo.org/pledin/2021/02/kubernetes-con-kind/)

# k3s

![k3s-logo](https://k3s.io/images/logo-k3s.svg =100px)

A diferencia de las opciones anteriores, k3s es una distribución de kubernetes que sí está pensada para poner en producción, pero en unas circunstancias peculiares como son su uso para IoT, edge computing y en general para configurar clusters de kubernetes en sistemas de pocos recursos (k3s es por ejemplo la opción más adecuada para usar kubernetes en la arquitectura arm). k3s no es un proyecto oficial de kubernetes, sino que lo comenzó a desarrollar la empresa [Rancher](https://rancher.com/) y hoy en día lo mantiene la [Cloud Native Computing Foundation](https://www.cncf.io/).

Los pasos para la instalaciónde k3s están disponibles en:

* [https://rancher.com/docs/k3s/latest/en/installation/](https://rancher.com/docs/k3s/latest/en/installation/)

# Conclusión

Aunque existen múltiples de instalación de kubernetes, en este curso utilizaremos minikube que es el proyecto más maduro y que consideremos más adecuado para comenzar y centrarnos directamente en el uso de kubernetes, obviando inicialmente los detalles de la instalación de kubernetes, que realmente es un proceso complejo y que no es lo más adecuado para empezar.