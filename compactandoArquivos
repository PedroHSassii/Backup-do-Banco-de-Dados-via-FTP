#!/bin/sh

mkdir /temporario/
#Configuracao para acesso a pasta
cd /bkp/delta/backup/

DATA=`ls -la --format=single-column | tail -1`

# diretorio do backup
DIRETORIOFONTE="/bkp/delta/backup/"$DATA

# diretorio aonde sera feito o backup
DIRETORIOARQBCK="/temporario/"

# Entrando no diretorio de backup
cd $DIRETORIOARQBCK

# Listando Diretorio
ls -l

# fazendo o backup
cp $DIRETORIOFONTE/* $DIRETORIOARQBCK

# espere por segundos
sleep 5

FTPSERVER="palmeiradasmissoes-rs.com.br"
LOCALDIR="/atual/"

# conecte-se ao servidor FTP e envie o arquivo

ftp -p $FTPSERVER << FTP

remove /antigo/*

rename atual antigo

mkdir atual

cd $LOCALDIR

ls -l

put ComprasG-$DATA.rar

put EstoqueG-$DATA.rar

put Folha_RH_RPPSG-$DATA.rar

put PatrimonioG-$DATA.rar

put Sapo_RPPSG-$DATA.rar

put EducacaoG-$DATA.rar

put Folha_RHG-$DATA.rar

put FrotasG-$DATA.rar

put SAPOG-$DATA.rar

put TributosG-$DATA.rar

cd

rmdir /antigo/*
bye
EOF
FTP

rm -rf /temporario/*
