# Explore Splunk in Kubernetes

NOTE: the container is started with --accept-license arg. What are the
actual
[terms](https://www.splunk.com/en_us/legal/splunk-software-license-agreement.html)?
See
[here](https://splunk.github.io/docker-splunk/advanced/LICENSE_INSTALL.html)
for more. The
[Section](https://splunk.github.io/docker-splunk/advanced/LICENSE_INSTALL.html#splunk-free-license)
seems to suggest the default ist 30-Day Trial.  There appears to be a
Splunk
[Free](https://docs.splunk.com/Documentation/Splunk/8.0.2/Admin/MoreaboutSplunkFree)
offering with limited functionality.

    kubectl create namespace hello-splunk
    kubectl config set-context --current --namespace=hello-splunk
    kubectl apply -k ./k3s

Then  Navigate to  [URL](http://splunk.localhost)  and  login as  User
"admin" with the password supplied in the Config.

See Docker [Hub](https://hub.docker.com/r/splunk/splunk) and
[docker-splunk](https://github.com/splunk/docker-splunk) on GitHub.
There are some strings attached to the
[support](https://splunk.github.io/docker-splunk/SUPPORT.html)
contract.

See Container Usage:

    kubectl exec ... /sbin/entrypoint.sh help

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
