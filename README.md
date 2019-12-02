# Grafana SimpleJson Datasource Backend in Clojure

A Clojure Implementation of the Data Source Backend for
[SimpleJson](https://grafana.com/grafana/plugins/grafana-simple-json-datasource)
Grafana Plugin.

## Usage

Start Grafana

    docker run -d -p 3000:3000 --name=grafana \
        -e "GF_INSTALL_PLUGINS=grafana-simple-json-datasource" grafana/grafana

and  configure   a  SimpleJson  Datasource  pointing   to  your  host,
e.g. http://192.168.0.1:8080.   Beware that localhost inside  a Docker
container does not point to the Docker Host. You may need to configure
Proxy  in the  Container environment  if  you are  behind a  corporate
Firewall, e.g.:

    docker run ... -e "https_proxy=..." ...

## Kubernetes

    kubectl create namespace datasource-clj
    kubectl config set-context --current --namespace=datasource-clj
    kubectl apply -k ./k3s

## License

Copyright © 2019 Alexei Matveev <alexei.matveev@gmail.com>

This program and the accompanying materials are made available under the
terms of the Eclipse Public License 2.0 which is available at
http://www.eclipse.org/legal/epl-2.0.

This Source Code may also be made available under the following Secondary
Licenses when the conditions for such availability set forth in the Eclipse
Public License, v. 2.0 are satisfied: GNU General Public License as published by
the Free Software Foundation, either version 2 of the License, or (at your
option) any later version, with the GNU Classpath Exception which is available
at https://www.gnu.org/software/classpath/license.html.
