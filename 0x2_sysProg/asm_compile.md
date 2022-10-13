# Assembly assembly Instructions into object file and link

nasm -f [elf32 | elf64] -o [object_file] [assembly_file]

ld -m elf64 -o [executable_name] [object_file]
