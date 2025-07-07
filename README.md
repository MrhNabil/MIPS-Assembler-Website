# MIPS Assembler Website

This is a simple, single-page interactive web application that functions as a MIPS assembler. It allows users to input MIPS assembly instructions and instantly see their 32-bit binary machine code representation. Built with **HTML**, **Tailwind CSS** for styling, and **vanilla JavaScript** for the core assembly logic, it provides a hands-on tool for learning and verifying MIPS instruction formats.

---

## 🔧 Features

- **Live Assembly:** Convert MIPS assembly instructions to binary machine code in real-time.
- **Instruction Support:** Handles a range of R-type, I-type, and J-type MIPS instructions, including common pseudo-instructions.
- **User-Friendly Interface:** Clean and responsive design using Tailwind CSS.
- **Educational Tool:** Helps in understanding the direct translation from assembly to binary.

---

## ✅ Supported Instructions

### 🟩 R-Type Instructions
- `add`, `addu` – Add, Add Unsigned  
- `sub`, `subu` – Subtract, Subtract Unsigned  
- `and`, `or`, `xor`, `nor` – Logical Operations  
- `slt`, `sltu` – Set Less Than (signed and unsigned)  
- `sll`, `srl`, `sra` – Shift Left/Right (Logical/Arithmetic)  
- `jr` – Jump Register  
- `mult`, `div` – Multiply, Divide  
- `mfhi`, `mflo` – Move From HI/LO Registers

### 🟨 I-Type Instructions
- `addi`, `addiu` – Add Immediate (signed and unsigned)  
- `andi`, `ori`, `xori` – Logical Immediate Operations  
- `lui` – Load Upper Immediate  
- `lw`, `sw` – Load/Store Word  
- `lb`, `lbu` – Load Byte (signed and unsigned)  
- `lh`, `lhu` – Load Halfword (signed and unsigned)  
- `sb`, `sh` – Store Byte, Store Halfword  
- `beq`, `bne` – Branch if Equal / Not Equal  
- `slti`, `sltiu` – Set Less Than Immediate (signed and unsigned)

### 🟥 J-Type Instructions
- `j` – Jump  
- `jal` – Jump and Link

### ⚙️ Pseudo-Instructions
- `move` → translates to `addu`  
- `nop` → translates to `sll $zero, $zero, 0`  
- `li` → translated if value fits 16-bit signed immediate; otherwise returns error

---

## 🚀 How to Use

1. **Open `index.html`:** Simply open the file in any modern web browser.
2. **Enter Instruction:** Type a MIPS instruction into the input field.  
   Examples:
   - `add $t0, $s1, $s2`
   - `lw $t0, 8($sp)`
   - `beq $t1, $t2, -4`
3. **Assemble:** Click the "Assemble" button or press **Enter**.
4. **View Output:** The binary code will appear. If the input is invalid or unsupported, an error will be shown.

---

## 🧠 Technical Details

- **Client-side only** – Fully implemented in vanilla JavaScript.
- **Utility Functions:**
  - `regToNum(regName)` – Maps register names like `$t0` or `r8` to their numeric values.
  - `toBinary(value, bits)` – Converts integer to fixed-length two's complement binary.
- **Instruction Definitions:**
  - `R_TYPE_FUNCTS` – Maps R-type mnemonics to opcode/funct codes.
  - `I_TYPE_OPCODES`, `J_TYPE_OPCODES` – Maps I/J-type instructions to opcodes.
- **Parsing Logic:**
  - `assembleMipsJS` function handles:
    - Instruction type detection
    - Operand parsing (registers, immediates, offsets, etc.)
    - Pseudo-instruction translation
    - Final 32-bit binary generation
- **Styling:** Done entirely using Tailwind CSS.

---

## 💻 Setup and Deployment

### 🧩 Clone the Repository
```bash
git clone https://github.com/MrhNabil/MIPS-Assembler-Website.git
cd MIPS-Assembler-Website
