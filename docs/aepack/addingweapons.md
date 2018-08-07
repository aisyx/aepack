# Adding Weapons

### Damage

**Damage** is defined in the first line of the long description:

```
^#7c7c7c;${Calibre} = ^white;${joules:0:2}^#7c7c7c;${joules:2:}J
```

1. Take the energy of the round and isolate the first two digits.
2. Set `/primaryAbility/baseDps` equal to those digits.

### Rounds per Minute

**RPM** is defined in the second line of the long description:

```
^#7c7c7c;Rate of fire = ^white;${rpm}^#7c7c7c;rpm
```

1. Take the amount of time (x) it takes to expend a magazine's capacity (y).
2. RPM = `( y / x ) * 60`.

### Pricing

The price in pixels can be determined as follows:

```python
(dmg * rpm) // accuracy
```
