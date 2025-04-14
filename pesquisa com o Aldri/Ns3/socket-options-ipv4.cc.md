- O script simula uma rede com 2 nós
- Estão conectados utilizando CSMA (Carrier-sense multiple access): É um protocolo MAC onde um nó verifica a ausência de tráfico antes de transmitir pelo meio
- Objetivos:
	- Entenda como sockets são criados e configurados:
		- nós são criados usando `NodeContainer`
		- instala o protocolo de internet com `InternetStackHelper`
		- `CsmaHelper` para criar o canal csma
		- `Ipv4AddressHelper` para colocar o ip no nó, ip base é `10.1.1.0` e a mascara de subrede `255.255.255.0`
		- Cria o socket receptor em n1
			- Os nós são criados a partir do número 0
```C
TypeId tid = TypeId::LookupByName ("ns3::UdpSocketFactory");
Ptr<Socket> recvSink = Socket::CreateSocket (n.Get (1), tid);
InetSocketAddress local = InetSocketAddress (Ipv4Address::GetAny (), 4477);
recvSink->SetIpRecvTos (ipRecvTos);
recvSink->SetIpRecvTtl (ipRecvTtl);
recvSink->Bind (local);
recvSink->SetRecvCallback (MakeCallback (&ReceivePacket));
```

- Cria o socket emissor em n0

```C
Ptr<Socket> source = Socket::CreateSocket (n.Get (0), tid);
InetSocketAddress remote = InetSocketAddress (i.GetAddress (1), 4477);
```

- TOS: é o tipo de serviço, uma parte co cabeçalho ipv4 que especifica a prioridade e o tipo de tratamento que o pacote deve receber ao ser roteado pela rede
- TTL: time to live, indica o número de máximo de saltos que um pacote ip pode percorrer através dos roteadores antes de res descartado.