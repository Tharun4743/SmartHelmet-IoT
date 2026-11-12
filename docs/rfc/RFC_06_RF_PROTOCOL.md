# RFC-06: Dual-Unit RF 433MHz Frame Specification

- Frame Format: [SYNC_0xAA, SYNC_0x55, SEQ_NUM, PAYLOAD_8B, CRC16_2B]
- Integrity: CRC-16-CCITT polynomial 0x1021
- Fault Tolerance: 3-packet rolling heartbeat with 800ms timeout