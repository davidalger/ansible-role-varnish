# Role: Varnish 4.1
This role installs and configures Varnish 4.1 from the public RPM on RHEL 6 and RHEL 7.

## Usage Information

For single-instance usage, simple assign the varnish role to the server in your playbook.

For dual-instance usage, reference the following role assignments for an example:

      roles:
        - name: varnish
        - name: varnish
          varnish_instance_name: stage
          varnish_restart_handler: restart varnish-stage
          varnish_listen_port: 6091
          varnish_admin_listen_port: 6092
      handlers:
        - name: restart varnish-stage
          service: name=varnish-stage state=restarted
