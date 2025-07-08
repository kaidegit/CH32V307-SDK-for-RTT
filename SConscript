import rtconfig
from building import *


# The set of source files associated with this SConscript file.

sdk_path = os.path.join("EVT", "EXAM", "SRC")

src = Glob(os.path.join(sdk_path, "Core", "*.c")) + \
    Glob(os.path.join(sdk_path, "Peripheral", "src", "*.c"))
src += Split('''
rtt-patch/ch32v30x_it.c
rtt-patch/system_ch32v30x.c
rtt-patch/startup_ch32v30x.S
''')

path = [
    os.path.join(sdk_path, "Core"),
    os.path.join(sdk_path, "Peripheral", "inc"),
    patch_path
]

group = DefineGroup(
    'Libraries',
    src,
    depend=['PKG_USING_CH32V307_SDK'],
    CPPPATH=path
)

Return('group')
