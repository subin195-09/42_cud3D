# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: skim <skim@student.42seoul.kr>             +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2020/12/13 00:33:36 by skim              #+#    #+#              #
#    Updated: 2021/02/26 16:22:28 by skim             ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

NAME = cub3d
GNL = libgnl.a
LIBFT = libft.a

CC = gcc
CFLAGS = -Wall -Werror -Wextra

OPENGNL = libmlx.dylib

LMLX = libmlx.dylib libmlx.a

INC_DIR = includes
MLX_DIR = ./mlx
GNL_DIR = ./GetNextLine
LIB_DIR = ./libft
SRCS_DIR = ./srcs
OBJS_DIR = ./objs

SRCS = start.c

SRCS = $(addprefix $(SRCS_DIR)/, \
	ft_printf.c ft_check_format.c ft_make_result.c \
	ft_make_result_int.c ft_make_result_int_second.c ft_make_result_int_third.c \
	ft_make_result_char.c ft_make_result_char_encoder.c \
	ft_make_result_base.c ft_make_result_base_second.c \
	ft_make_result_ptr.c ft_make_result_per.c \
	ft_make_result_float.c \
	ft_zero_check.c)

all : $(NAME)

$(NAME) : $(LIBFT) $(GNL)
	$(CC) $(CFLAGS) -I $(MMS_DIR) -I $(OPENGNL_DIR) $(LMLX) $(SRCS) -o $(NAME)

$(LIBFT) :
	@make -C $(LIB_DIR)
	@cp $(LIB_DIR)/$(LIBFT) .

$(GNL) :
	@make -C $(GNL_DIR)
	@cp $(GNL_DIR)/$(GNL) .

clean :
	rm -rf $(NAME)
	rm -rf $(LMLX)

fclean : clean
	make -C $(MMS_DIR) clean
	make -C $(OPENGNL_DIR) clean

re : fclean all

bonus : all

00 :
	$(CC) -I$(INC_DIR) -L$(MLX_DIR) -lmlx -framework OpenGL -framework AppKit 00.start.c
	./a.out
	rm -rf ./a.out

01-2 :
	$(CC) -I$(INC_DIR) -L./mlx -lmlx -framework OpenGL -framework AppKit 01-2.2d_map.c
	./a.out
	rm -rf ./a.out

01 :
	$(CC) -I$(INC_DIR) -L./mlx -lmlx -framework OpenGL -framework AppKit 01.untextured.c
	./a.out
	rm -rf ./a.out

02 :
	$(CC) -I$(INC_DIR) -L./mlx -lmlx -framework OpenGL -framework AppKit 02.textured.c
	./a.out
	rm -rf ./a.out

03 :
	$(CC) -I$(INC_DIR) -L./mlx -lmlx -framework OpenGL -framework AppKit 03.img_textured.c
	./a.out
	rm -rf ./a.out

04 :
	$(CC) -I$(INC_DIR) -L./mlx -lmlx -framework OpenGL -framework AppKit 04.img_floor.c
	./a.out
	rm -rf ./a.out

05 :
	$(CC) -I$(INC_DIR) -L./mlx -lmlx -framework OpenGL -framework AppKit 05.sprite.c
	./a.out
	rm -rf ./a.out


06 : $(GNL) $(LIBFT)
	@$(CC) $(CFLAGS) -I$(INC_DIR) -I$(GNL_DIR)/$(INC_DIR) -I$(LIB_DIR)/$(INC_DIR) -I$(MLX_DIR) -L$(LIB_DIR) -L$(MLX_DIR) -L$(GNL_DIR) -lgnl -lft -lmlx -framework OpenGL -framework AppKit 06.map_par.c
	@ ./a.out
	@ rm -rf ./a.out
	@ rm tmp_map

test : $(GNL) $(LIBFT)
	@$(CC) $(CFLAGS) -I$(INC_DIR) -I$(GNL_DIR)/$(INC_DIR) -I$(LIB_DIR)/$(INC_DIR) -I$(MLX_DIR) \
	-L./ -lgnl -lft -lmlx \
	-framework OpenGL -framework AppKit -o cub3d cub3d.c
	@ ./cub3d
	@ rm -rf ./cub3d
	@ rm tmp_map
