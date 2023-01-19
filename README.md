# unbound-plugin-for-munin

only for system freeBSD

<h2>step1</h2>

add this code to: /usr/local/etc/munin/plugin-conf.d/plugins.conf

<pre>
[unbound*]
user root
env.statefile /var/munin/plugin-state/nobody/unbound.state
env.unbound_conf /usr/local/etc/unbound/unbound.conf
env.unbound_control /usr/local/sbin/unbound-control
env.spoof_warn 1000
env.spoof_crit 100000
</pre>


<h2>step2</h2>

<pre>
ln -s /usr/local/share/munin/plugins/unbound_munin_ /usr/local/etc/munin/plugins/unbound_munin_by_class
ln -s /usr/local/share/munin/plugins/unbound_munin_ /usr/local/etc/munin/plugins/unbound_munin_by_flags
ln -s /usr/local/share/munin/plugins/unbound_munin_ /usr/local/etc/munin/plugins/unbound_munin_by_opcode
ln -s /usr/local/share/munin/plugins/unbound_munin_ /usr/local/etc/munin/plugins/unbound_munin_by_rcode
ln -s /usr/local/share/munin/plugins/unbound_munin_ /usr/local/etc/munin/plugins/unbound_munin_by_type
ln -s /usr/local/share/munin/plugins/unbound_munin_ /usr/local/etc/munin/plugins/unbound_munin_histogram
ln -s /usr/local/share/munin/plugins/unbound_munin_ /usr/local/etc/munin/plugins/unbound_munin_memory
ln -s /usr/local/share/munin/plugins/unbound_munin_ /usr/local/etc/munin/plugins/unbound_munin_queue
ln -s /usr/local/share/munin/plugins/unbound_munin_ /usr/local/etc/munin/plugins/unbound_munin_hits
</pre>

<h2>step3</h2>

<pre>
service unbound restart
service munin-node restart
</pre>

done!

resource: https://niamweb.blogspot.com/2023/01/unbound-plugin-untuk-munin.html
