k3s Single Node Install
========================

.. _installation:

On the node:

.. code-block:: console

    curl -sfL https://get.k3s.io | sh -

.. code-block:: console

    sudo systemctl status k3s.service
    sudo kubectl cluster-info
    sudo kubectl get node
    sudo cat /etc/rancher/k3s/k3s.yaml
    sudo ufw allow 6443/tcp
    sudo ufw reload
    sudo sysctl fs.inotify.max_user_watches=655360
    sudo sysctl fs.inotify.max_user_instances=1280

On personal machine (assuming osx): 

- Install
.. code-block:: console

    brew install kubectl

- Config
.. code-block:: console

    mkdir -p ~/.kube
    touch ~/.kube/config
    chown $(id -u):$(id -g) ~/.kube/config
    chmod 600 ~/.kube/config

Copy `sudo cat /etc/rancher/k3s/k3s.yaml` (from node) to above

- Test

.. code-block:: console

    kubectl version --output=yaml
    kubectl cluster-info
    kubectl get node