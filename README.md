# short-pipe-v1
short reads, standard scheme, nt database (IMG/VR)

Pipeline Directory Expected Structure:
-----------------------------
- raw_reads/            
- results/              
  - fastqc/             
  - trimmed_reads/      
  - kraken2/            
  - viral_reads/        
  - assemblies/         
  - centrifuge/         
  - deepvirfinder/      
  - virsorter2/         
  - reports/            
- config/
  - config.yaml
  - deepvirfinder_env.yaml
  - virsorter2_env.yaml               
- scripts/
  - generate_report.py              
- tools/
  - KrakenTools/
  - DeepVirFinder/
  - VirSorter2 	                
- Snakefile

Additional Files:
--------------------------
- setup_environment.sh - Bash script to install the env (including third party tools)
- IMGvr_to_centrifuge_DB.py - Python script to transform IMG/VR database files to usable input for "centrifuge-build"  

Steps to Run the Pipeline:
--------------------------
1. Place raw reads in 'raw_reads/' folder, named as '<sample>_R1.fastq.gz' and '<sample>_R2.fastq.gz'.
2. Update 'config/config.yaml' with your sample names, database paths, and thread settings.
3. Activate the pipeline environment:
   conda activate virpipe_short1
4. Run the pipeline with:
   snakemake --cores <number_of_cores> --use-conda
4.1 If your Mamba version is less than 2.* you can add "--conda-frontend mamba" to speed up the subenvs building


<img src="https://github.com/user-attachments/assets/98fc6a5e-1190-4042-a77d-8929199fe734" width="300" height="550">
