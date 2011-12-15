# Copyright (c) Istituto Nazionale di Fisica Nucleare (INFN). 2006-2010.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#
#
# Authors: Alberto Forti <alberto.forti@cnaf.infn.it>
#

AC_PREREQ([2.59])
AC_INIT([storm pre assembled configuration], [1.0.0])
AC_CONFIG_AUX_DIR([./project])
AM_INIT_AUTOMAKE([1.6.3 subdir-objects])
AC_CONFIG_SRCDIR([etc/siteinfo/storm.def.template.in])

# Release number
osdist=`cat /etc/redhat-release | awk 'BEGIN {FS="release "} {print $2}'| awk 'BEGIN {FS="."} {print $1}'`
AC_SUBST([STORM_UTILITY_SO], [sl$osdist])
AC_SUBST([STORM_UTILITY_AGE_NUMBER], [1])

# Notices.
AC_COPYRIGHT([See LICENCE file for details])
AC_REVISION([$Revision: $])

#Environment.
WORKDIR=`pwd`
AC_SUBST(WORKDIR)

DEFAULT_RPM_DIR=`pwd`

AC_PROG_CC
AC_PROG_CXX
AC_PROG_LN_S
AC_PROG_MAKE_SET
AC_PROG_LIBTOOL
AM_PROG_CC_C_O
AC_PROG_INSTALL

AC_C_CONST
AC_TYPE_SIZE_T

AC_STORM

# ========================================================================
# RPM directory
# ========================================================================
AC_MSG_CHECKING([for RPM directory])
if test -z $RPMD; then
    RPMD=$DEFAULT_RPM_DIR
    RPMBD=$DEFAULT_RPM_DIR/rpm/tmp
fi
if test ! \( -d $RPMD \); then
    AC_MSG_RESULT([no such directory "$RPMD"])
fi
if test ! \( -d $RPMBD \); then
    AC_MSG_RESULT([no such directory "$RPMBD"])
fi
AC_MSG_RESULT(["$RMPD" found])
AC_MSG_RESULT(["$RMPBD" found])
AC_SUBST([RPM_DIR], [$RPMD])
AC_SUBST([RPM_BUILD_DIR], [$RPMBD])

# Installation prefix
AC_PREFIX_DEFAULT([/etc])

# Configuration items
AM_CONFIG_HEADER([etc/autogen/config.h])

AC_CONFIG_FILES([Makefile])

AC_CONFIG_FILES([etc/Makefile])
AC_CONFIG_FILES([etc/siteinfo/Makefile])
AC_CONFIG_FILES([etc/siteinfo/storm.def.template])
AC_CONFIG_FILES([etc/siteinfo/vo.d/Makefile])
AC_CONFIG_FILES([storm-pre-assembled-configuration.spec])

AC_OUTPUT

