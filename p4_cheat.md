## P4小抄

### 更新报文的checksum

```p4lang
control TopDeparser(inout Parsed_packet p, packet_out b) {
	// built-in function
	Checksum16() ck;
	apply {
		b.emit(p.ethernet);
		if (p.ip.isValid()) {
			ch.clear();
      	  p.ip.hdrChecksum = 16w0;
      	  ck.update(p.ip);
      	  p.ip.hdrChecksum = ck.get();
		}
		b.emit(p.ip)
	}
}


```

