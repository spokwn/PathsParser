# Paths Parser

Retrieves data about file paths found in `.txt` files.

## What does it do?
- **Parses** the paths from `.txt` files.
  - For example, a line like `0x1ffd7017eb0 (109): \??\C:\users\user\desktop\cheat.dll` would be parsed into `C:\users\user\desktop\cheat.dll`.
- **Checks digital signatures** for each file:
  - Checks for **Catalog** and **Authenticode** signatures.   
  - Reports **"Deleted"** if the file is not found.
  - Detects specific digital signatures (e.g., *Slinky* and *Vape*, which are known cheats).
  - Reports **"Signed"** or **"Not signed"** for each present file.
- **Applies generic checks** to each present file (more on generics below).
- **Checks for "replacements"** using the internal journal system for each file (Explorer, Copy, or Type patterns).

---

## How to Use

1. **Place your target paths in one or more of these files** (either in `C:\` or in the same folder as the program):
   - `search results.txt`
   - `paths.txt`
   - `p.txt`

   Each file can contain any number of lines. Lines that contain paths like `C:\somefolder\somefile.exe` will be automatically parsed. The code will ignore invalid entries or lines that do not contain a proper file path.

2. **Run the compiled executable** (e.g., `PathsParser.exe`).  

3. The console will display:
   - Whether each file is **present or deleted**.  
   - The **digital signature** status.  
   - Any **generic** or **specific detection** hits.  

4. When finished, the program will:
   - Write any found replacements to `replaces.txt` (in the same folder as the program).
   - **Review `replaces.txt`** to see the summary of replacement findings (if any).

---

## Generics

1. **Generic A**: Basic strings for autoclickers  
2. **Generic A2**: Import combination for autoclickers  
3. **Generic A3**: Generic detection for C# autoclickers  
4. **Generic B**: Generic protection detection for non-C# files  
5. **Generic B2**: Generic protection detection for non-C# files  
6. **Generic B3**: Generic protection detection for non-C# files  
7. **Generic B4**: Generic protection detection for non-C# files  
8. **Generic B5**: Generic protection detection for non-C# files  
9. **Generic B6**: Generic protection detection for non-C# files  
10. **Generic B7**: Generic protection detection for non-C# files  
11. **Generic C**: Basic generic protection detection for C# files  
12. **Generic D**: Well done generic protection detection for C# files  
13. **Generic E**: Basic generic protection detection for C# and compiled Python files  
14. **Generic F**: Advanced generic detection for packed executables  
15. **Generic F2**: Advanced generic detection for packed executables  
16. **Generic F3**: Advanced generic detection for packed executables  
17. **Generic F4**: Advanced generic detection for packed executables  
18. **Generic F5**: Advanced generic detection for packed executables  
19. **Generic F6**: Advanced generic detection for **very** packed executables  
20. **Generic F7**: Advanced generic detection for **SUPER** packed executables  
21. **Generic G**: Advanced generic detection for suspicious injector executables  
22. **Generic G2**: Advanced generic detection for suspicious injector executables  
23. **Generic G3**: Advanced generic detection for suspicious injector executables  
24. **Generic G4**: Advanced generic detection for suspicious injector executables  
25. **Generic G5**: Advanced generic detection for suspicious injector executables  
26. **Generic G6**: Advanced generic detection for suspicious injector executables  
27. **Generic G7**: Advanced generic detection for suspicious PE injector executables  
28. **Generic G8**: Advanced generic detection for suspicious PE injector executables  
29. **Specific A**: Detects some free cheats by simple string signatures  
30. **Specific B**: Detects some paid cheats using advanced methods

> **Note:** A2 and F (or F2, F3, etc.) generics may cause **occasional false positives** but are maintained to ensure real cheats are detected.

---

## TODO

- [ ] Add a GUI