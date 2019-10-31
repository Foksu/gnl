# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: vvaltone <marvin@42.fr>                    +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2019/10/22 11:43:38 by vvaltone          #+#    #+#              #
#    Updated: 2019/10/31 17:52:34 by vvaltone         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

NAME = libft.a

COMP = gcc -Wall -Werror -Wextra -I includes -c -o

OBJ_DIR = ./obj/
SRC_DIR = ./srcs/

CFIND = $(shell find $(SRC_DIR) -maxdepth 1 -type f | grep -E "\.c$$")
CFILE = $(notdir $(CFIND))
OFILE = $(CFILE:%.c=%.o)

OBJ = $(addprefix $(OBJ_DIR), $(OFILE))

all: $(OBJ_DIR) $(NAME)

$(OBJ_DIR):
	@mkdir -p $(OBJ_DIR)

$(NAME): $(OBJ)
	@ar rc $(NAME) $(addprefix $(OBJ_DIR), $(OFILE))
	@ranlib $(NAME)

$(OBJ): $(CFIND)
	@$(MAKE) $(OFILE)

$(OFILE):
	@$(COMP) $(OBJ_DIR)$@ $(SRC_DIR)$(@:%.o=%.c)

clean:
	@/bin/rm -rf $(OBJ_DIR)

fclean: clean
	@/bin/rm -f $(NAME)

re: fclean all

.PHONY: clean fclean re
