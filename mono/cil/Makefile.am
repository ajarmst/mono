include $(top_srcdir)/mk/common.mk

# opcode.def is not built by default -- based on timestamps.
# CI does not have the dependencies installed (perl, XML::Parser).
# The derived file is checked in.
opcode.def: make-opcodes-def.pl cil-opcodes.xml
	perl $(srcdir)/make-opcodes-def.pl $(srcdir)/cil-opcodes.xml $@.tmp
	mv $@.tmp $@

defdir = $(includedir)/mono-$(API_VER)/mono/cil
def_DATA = opcode.def

xmldir = $(datadir)/mono-$(API_VER)/mono/cil
xml_DATA = cil-opcodes.xml

EXTRA_DIST=tables.def opcode.def make-opcodes-def.pl make-opcode-def.xsl $(xml_DATA) $(def_DATA)
