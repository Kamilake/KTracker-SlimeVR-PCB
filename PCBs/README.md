# Custom assembly using Kikit JLC


## Panalize and Fab
```batch
kikit panelize ^
    -p :jlcTooling ^
    --layout "grid; rows: 5; cols: 10;" ^
    --source "tolerance: 1000mm" ^
    --tabs full ^
    --cuts vcuts ./KamiTrack.kicad_pcb ^
    KamiTrack_panel.kicad_pcb

kikit fab jlcpcb ^
    --assembly ^
    --schematic ./KamiTrack.kicad_sch ^
    --ignore J1 ^
    --no-drc ./KamiTrack_panel.kicad_pcb ^
    ./fab
```

## Only Fab

### Using internal MPU-6050+QMC5883L and bottom Lipo
```batch
kikit fab jlcpcb ^
    --assembly ^
    --schematic ./KamiTrack.kicad_sch ^
    --ignore BT1,J3,J4,J5 ^
    --no-drc ./KamiTrack.kicad_pcb ^
    "./Gerber/Using internal MPU-6050+QMC5883L and bottom Lipo"
```
### Using internal MPU-6050+QMC5883L and Left side Lipo
```batch
kikit fab jlcpcb ^
    --assembly ^
    --schematic ./KamiTrack.kicad_sch ^
    --ignore BT1,J1,J4,J5 ^
    --no-drc ./KamiTrack.kicad_pcb ^
    "./Gerber/Using internal MPU-6050+QMC5883L and Left side Lipo"
```

### Using GY-521 and bottom Lipo
```batch
kikit fab jlcpcb ^
    --assembly ^
    --schematic ./KamiTrack.kicad_sch ^
    --ignore U8,U3,R20,R21,C16,C12,C11,R12,R11,BT1,J3,J4,J5 ^
    --no-drc ./KamiTrack.kicad_pcb ^
    "./Gerber/Using GY-521 and bottom Lipo"

```

### Using GY-521 and 18650
```batch
kikit fab jlcpcb ^
    --assembly ^
    --schematic ./KamiTrack.kicad_sch ^
    --ignore U8,U3,R20,R21,C16,C12,C11,R12,R11,J1,J3,J4,J5 ^
    --no-drc ./KamiTrack.kicad_pcb ^
    "./Gerber/Using GY-521 and 18650"

```
