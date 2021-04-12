Bind 9
=============

## Ситуация "Две сетевых карты и несколько DNS-серверов"

### Решение 1

Первая сеть 192.168.0.X
Вторая сеть 192.168.25.X

```
## named.conf.options

options {
	directory "/var/cache/bind";

	dnssec-validation no;

	allow-query { any; };
  recursion yes;

	listen-on-v6 { any; };
	forwarders {
		192.168.0.1;
		};
};

## named.conf.local

zone "orion.org" {
	type forward;
	forwarders {
		192.168.25.X;
		};
	forward only;
	};
zone "orion.web" {
	type forward;
	forwarders {
		192.168.25.X;
		};
	forward first;
	};
```

### Решения 2

[Установка приоритетов сетевых устройств](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/configuring_and_managing_networking/configuring-the-order-of-dns-servers_configuring-and-managing-networking)
