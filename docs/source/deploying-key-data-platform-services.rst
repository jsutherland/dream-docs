Deploying key data platform services
====================================

Install client dependencies 
---------------------------
n.b. assumes osx & aarm64 platform.

.. _clone repository:

Get the dream-deploy repo:

.. code-block:: console

    git clone git@github.com:jsutherland/dream-deploy.git

.. _install dependencies on client :

Install various client CLI tools:

.. code-block:: console

    cd ./dream-deploy
    make install-client-tools

Deploy common services to cluster
---------------------------------

.. code-block:: console

    cd ./dream-deploy
    make deploy-k8s-dashboard
    make deploy-k8s-metrics-server

Deploy app services to cluster
--------------------------------------

First do:

.. code-block:: console

    cd ./dream-deploy && \
    make deploy-kubeflow && \
    make deploy-datahub-prereqs && \

Then:

.. code-block:: console

    make deploy-datahub

Optional services:

.. code-block:: console

    make deploy-minio (&& make deploy-minio-default-tenant)
    make deploy-spark
