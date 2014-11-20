# Docker image build file.
#   ______  ____             _              ______
#  / / / / |  _ \  ___   ___| | _____ _ __  \ \ \ \
# / / / /  | | | |/ _ \ / __| |/ / _ \ '__|  \ \ \ \
# \ \ \ \  | |_| | (_) | (__|   <  __/ |     / / / /
#  \_\_\_\ |____/ \___/ \___|_|\_\___|_|    /_/_/_/
#
# TAG: yukpiz/ubuntu:develop

FROM ubuntu:14.10
MAINTAINER yukpiz<yukpiz@gmail.com>

# --- Package management {{{

# Update repository indexes
    RUN apt-get update

# Update packages
    RUN apt-get upgrade -y

# C, C++
    RUN apt-get install -y gcc
    RUN apt-get install -y make

# Lua(for Vim)
    RUN apt-get install -y lua5.1
    RUN apt-get install -y lua5.1-dev
    RUN apt-get install -y liblua5.1.0

# Development tools
    RUN apt-get install -y ctags
    RUN apt-get install -y git
    RUN apt-get install -y svn
    RUN apt-get install -y mercurial

# Utilities
    # ASCII ART Creation Tool
    RUN apt-get install -y figlet
    RUN apt-get install -y wget

# Text Editor

# }}}


