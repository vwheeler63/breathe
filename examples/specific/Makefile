#
# This file was generated from Makefile.in on Sat Dec 13 12:17:28 GMT 2008
#

DOXYGEN   ?= `which doxygen`
TMAKEPATH =
ENV       = env TMAKEPATH=$(TMAKEPATH)
TMAKE     =
MAKE      = /usr/bin/make
PERL      = /usr/bin/perl
RM        = rm -f
CP        = cp
VERSION   = 1.5.7.1
INSTALL   = /tmp
INSTTOOL  = /usr/bin/install
DOXYDOCS  = ..
DOCDIR    = $(INSTALL)/share/doc/packages/doxygen
QTDIR     =
HAVE_DOT  = /usr/bin/dot

projects  = nutshell alias rst inline namespacefile array inheritance \
			members userdefined fixedwidthfont latexmath functionOverload \
			image name union group struct struct_function qtsignalsandslots lists \
			headings links parameters template_class template_class_non_type \
			template_function template_type_alias template_specialisation \
			enum define interface xrefsect tables \
			cpp_anon cpp_concept cpp_enum cpp_union cpp_function cpp_friendclass \
			cpp_inherited_members cpp_trailing_return_type cpp_constexpr_hax \
			cpp_function_lookup cpp_ns_template_specialization \
			c_file c_struct c_enum c_typedef c_macro c_union membergroups \
			simplesect code_blocks dot_graphs

special   = programlisting decl_impl multifilexml auto class typedef

xmls := $(foreach project, $(projects), $(project)/xml/index.xml)

special_xmls = $(foreach project, $(special), $(project)/xml/index.xml)

all: $(xmls) $(special_xmls)

clean:
	rm -rf $(projects) $(special)


# General pattern
# ---------------

$(xmls): %/xml/index.xml: %.cfg %.h
	$(DOXYGEN) $<


# Special Cases
# -------------

programlisting/xml/index.xml: programlisting.h programlisting.cfg programlistinginclude.txt
	$(DOXYGEN) programlisting.cfg

decl_impl/xml/index.xml: decl_impl.h decl_impl.cpp decl_impl.cfg
	$(DOXYGEN) decl_impl.cfg

multifilexml/xml/index.xml: multifile/one/Util.h multifile/two/Util.h multifile.cfg
	$(DOXYGEN) multifile.cfg

auto/xml/index.xml: auto_class.h auto_function.h auto.cfg
	$(DOXYGEN) auto.cfg

class/xml/index.xml: class.h class.cpp class.cfg
	$(DOXYGEN) class.cfg

typedef/xml/index.xml: typedef.h typedef.cfg
	$(DOXYGEN) typedef.cfg
