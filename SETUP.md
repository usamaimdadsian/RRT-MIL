Features are extracted using CLAM
where h5_files and pt_files folders are generated containing features

1. copy the slide_name_df.csv file in the features folder (folder that contains h5_files and pt_files folders) and change it name to "lable.csv" remove header line and first column of that csv file

2. In the dataloader in TCGADataset constructor create a mapping from class to integer id. and in forward function first convert the class to integer before returning.

3. Create results folder

4. Run the following command

`
   "program": "${workspaceFolder}/main.py",
   "console": "integratedTerminal",
   "args": [
       "--project=tcga_lung",
       "--datasets=tcga",
       "--tcga_sub=lung",
       "--dataset_root=/mnt/linux/programmes/itu/semester5/thesis1/CLAM/features",
       "--model_path=results",
       "--cv_fold=5",
       "--model=rrtmil",
       "--pool=attn",
       "--n_trans_layers=2",
       "--da_act=tanh",
       "--title=lung_r50_rrtmil",
       "--epeg_k=17",
       "--crmsa_k=3",
       "--crmsa_heads=1",
       "--input_dim=1024",
       "--seed=2021"
   ]

`