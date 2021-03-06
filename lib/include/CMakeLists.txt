#
# Copyright (C) 2015-2016 Virgil Security Inc.
#
# Lead Maintainer: Virgil Security Inc. <support@virgilsecurity.com>
#
# All rights reserved.
#
# Redistribution and use in source and binary forms, with or without
# modification, are permitted provided that the following conditions are
# met:
#
#     (1) Redistributions of source code must retain the above copyright
#     notice, this list of conditions and the following disclaimer.
#
#     (2) Redistributions in binary form must reproduce the above copyright
#     notice, this list of conditions and the following disclaimer in
#     the documentation and/or other materials provided with the
#     distribution.
#
#     (3) Neither the name of the copyright holder nor the names of its
#     contributors may be used to endorse or promote products derived from
#     this software without specific prior written permission.
#
# THIS SOFTWARE IS PROVIDED BY THE AUTHOR ''AS IS'' AND ANY EXPRESS OR
# IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
# WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
# DISCLAIMED. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY DIRECT,
# INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES
# (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
# SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION)
# HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT,
# STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING
# IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
# POSSIBILITY OF SUCH DAMAGE.
#

if (LIB_FILE_IO)
    set (EXCLUDE_FILE_IO_PATTERN "fake-stream")
else ()
    set (EXCLUDE_FILE_IO_PATTERN "stream")
endif ()

if (LIB_LOW_LEVEL_API)
    install (DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}/" DESTINATION "${INSTALL_INC_DIR_NAME}"
        FILES_MATCHING
        PATTERN "*.h"
        PATTERN "internal" EXCLUDE
        PATTERN ${EXCLUDE_FILE_IO_PATTERN} EXCLUDE
    )
else ()
    install (DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}/" DESTINATION "${INSTALL_INC_DIR_NAME}"
        FILES_MATCHING
        PATTERN "*.h"
        PATTERN "cms" EXCLUDE
        PATTERN "internal" EXCLUDE
        PATTERN "VirgilOID.h" EXCLUDE
        PATTERN "VirgilAsn1Reader.h" EXCLUDE
        PATTERN "VirgilAsn1Writer.h" EXCLUDE
        PATTERN "VirgilKDF.h" EXCLUDE
        PATTERN "PolarsslException.h" EXCLUDE
        PATTERN "VirgilKeyPairGenerator.h" EXCLUDE
        PATTERN "VirgilSymmetricCipher.h" EXCLUDE
        PATTERN "VirgilAsymmetricCipher.h" EXCLUDE
        PATTERN "VirgilRandom.h" EXCLUDE
        PATTERN "VirgilPBE.h" EXCLUDE
        PATTERN ${EXCLUDE_FILE_IO_PATTERN} EXCLUDE
    )
endif ()
