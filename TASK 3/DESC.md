### RISC-V Instruction Codes with Actual Instruction Formats

| Serial No. | Instruction                           | Instruction Format  | 32-Bit Instruction Code |
|------------|---------------------------------------|---------------------|--------------------------|
| 1          | `lui a0, 0x2b`                       | `U-type: [ imm[31:12] ][ rd ][ opcode ]`<br> `imm = 0x0002B`<br> `rd = x10`<br> `opcode = 0x37` | `0x0002B073`             |
| 2          | `addi sp, sp, -64`                   | `I-type: [ imm[11:0] ][ rs1 ][ funct3 ][ rd ][ opcode ]`<br> `imm = -64 (0xFFD0)`<br> `rs1 = x2`<br> `funct3 = 0x0`<br> `rd = x2`<br> `opcode = 0x13` | `0xFFD30313`             |
| 3          | `sd ra, 56(sp)`                      | `S-type: [ imm[11:5] ][ rs2 ][ rs1 ][ funct3 ][ imm[4:0] ][ opcode ]`<br> `imm = 56 (0x38)`<br> `rs2 = x1`<br> `rs1 = x2`<br> `funct3 = 0x2`<br> `opcode = 0x23` | `0x00E303B3`             |
| 4          | `jal ra, 1059c <printf>`             | `J-type: [ imm[20] ][ imm[10:1] ][ imm[11] ][ imm[19:12] ][ rd ][ opcode ]`<br> `imm = 0x059c (offset)`<br> `rd = x1`<br> `opcode = 0x6F` | `0x000FF06F`             |
| 5          | `lw s3, 12(sp)`                      | `I-type: [ imm[11:0] ][ rs1 ][ funct3 ][ rd ][ opcode ]`<br> `imm = 12 (0xC)`<br> `rs1 = x2`<br> `funct3 = 0x2`<br> `rd = x19`<br> `opcode = 0x03` | `0x00030383`             |
| 6          | `li s2, 0`                           | `I-type: [ imm[11:0] ][ rs1 ][ funct3 ][ rd ][ opcode ]`<br> `imm = 0x0`<br> `rs1 = x0`<br> `funct3 = 0x0`<br> `rd = x18`<br> `opcode = 0x13` | `0x00030393`             |
| 7          | `mv s1, s3`                          | `R-type: [ funct7 ][ rs2 ][ rs1 ][ funct3 ][ rd ][ opcode ]`<br> `rs1 = x19`<br> `rs2 = x19`<br> `rd = x9`<br> `funct3 = 0x0`<br> `funct7 = 0x0`<br> `opcode = 0x33` | `0x00018233`             |
| 8          | `beqz s3, 1015c <main+0xac>`         | `B-type: [ imm[12] ][ rs2 ][ rs1 ][ funct3 ][ imm[10:5] ][ imm[4:1] ][ imm[11] ][ opcode ]`<br> `imm = 0x0F4`<br> `rs1 = x19`<br> `rs2 = x0`<br> `funct3 = 0x0`<br> `opcode = 0x63` | `0x00048263`             |
| 9          | `slliw s0, s2, 0x2`                  | `R-type: [ funct7 ][ rs2 ][ rs1 ][ funct3 ][ rd ][ opcode ]`<br> `rs1 = x18`<br> `rs2 = x0`<br> `rd = x8`<br> `funct3 = 0x1`<br> `funct7 = 0x0`<br> `opcode = 0x33` | `0x00049283`             |
| 10         | `addw s0, s0, s2`                    | `R-type: [ funct7 ][ rs2 ][ rs1 ][ funct3 ][ rd ][ opcode ]`<br> `rs1 = x8`<br> `rs2 = x18`<br> `rd = x8`<br> `funct3 = 0x0`<br> `funct7 = 0x0`<br> `opcode = 0x33` | `0x00200033`             |
| 11         | `sext.w s1, a0`                      | `R-type: [ funct7 ][ rs2 ][ rs1 ][ funct3 ][ rd ][ opcode ]`<br> `rs1 = x10`<br> `rd = x9`<br> `funct3 = 0x0`<br> `funct7 = 0x0A`<br> `opcode = 0x33` | `0x000A4926`             |
| 12         | `bnez s1, 100f4 <main+0x44>`         | `B-type: [ imm[12] ][ rs2 ][ rs1 ][ funct3 ][ imm[10:5] ][ imm[4:1] ][ imm[11] ][ opcode ]`<br> `imm = 0x0F4`<br> `rs1 = x9`<br> `rs2 = x0`<br> `funct3 = 0x1`<br> `opcode = 0x63` | `0x00048263`             |
| 13         | `j 1013c <main+0x8c>`                | `J-type: [ imm[20] ][ imm[10:1] ][ imm[11] ][ imm[19:12] ][ rd ][ opcode ]`<br> `imm = 0x013C (offset)`<br> `rd = x0`<br> `opcode = 0x6F` | `0x000FF06F`             |
| 14         | `ld s2, 32(sp)`                      | `I-type: [ imm[11:0] ][ rs1 ][ funct3 ][ rd ][ opcode ]`<br> `imm = 32 (0x20)`<br> `rs1 = x2`<br> `funct3 = 0x3`<br> `rd = x18`<br> `opcode = 0x03` | `0x0002B383`             |
| 15         | `auipc gp, 0x1e`                     | `U-type: [ imm[31:12] ][ rd ][ opcode ]`<br> `imm = 0x1E000`<br> `rd = x28`<br> `opcode = 0x37` | `0x0001E073`             |
