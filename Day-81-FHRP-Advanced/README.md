# Day-81-FHRP-Advanced-HSRP

## Objective

Configure and verify HSRP (Hot Standby Router Protocol) to provide default gateway redundancy for end devices.

---

## Topology

           R1
            |
            |
          SW1
         / | \
        /  |  \
      PC0  |  PC1
           |
           |
          R2

---

## Device List

- 2 x Cisco 2911 Routers
- 1 x Cisco 2960 Switch
- 2 x PCs

---

## IP Addressing

### R1

| Interface | IP Address |
|------------|------------|
| G0/0 | 192.168.10.2/24 |

### R2

| Interface | IP Address |
|------------|------------|
| G0/1 | 192.168.10.3/24 |

### HSRP Virtual Gateway

| Virtual IP |
|------------|
| 192.168.10.1 |

### PC0

| Setting | Value |
|----------|--------|
| IP | 192.168.10.10 |
| Mask | 255.255.255.0 |
| Gateway | 192.168.10.1 |

### PC1

| Setting | Value |
|----------|--------|
| IP | 192.168.10.20 |
| Mask | 255.255.255.0 |
| Gateway | 192.168.10.1 |

---

## HSRP Configuration

### R1

- Priority: 120
- Preempt: Enabled
- State: Active

### R2

- Priority: 100
- Preempt: Enabled
- State: Standby

---

## Verification Commands

```cisco
show standby brief

show standby

show ip interface brief
```


---


