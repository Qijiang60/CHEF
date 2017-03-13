template, package, and service are just three of the many types of resources built into
the Chef DSL. The following code demonstrates using the template, package, and
service resources in Chef code:

template '/etc/resolv.conf' do
 source 'my_resolv.conf.erb'
 owner 'root'
 group 'root'
 mode '0644'
end
This declares a template resource in Chef ’s DSL. The template will be compiled
from the local file my_resolv.conf.erb, be owned by root:root, have 0644
permissions, and be placed at /etc/resolv.conf on the target machine (where Chef
evaluates the code).


package 'ntp' do
 action :upgrade
end
This declares a package resource in Chef ’s DSL. The “ntp” package will be
upgraded.

service 'apache2' do
 restart_command '/etc/init.d/apache2 restart'
end
This declares a service resource in Chef ’s DSL. The “apache2” service will be
accessible and manageable by Chef.
