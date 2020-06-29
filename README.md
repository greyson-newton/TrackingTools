# TrackingTools

export SCRAM_ARCH=slc7_amd64_gcc820

git clone https://github.com/cms-mual/Alignment.git -b CMSSW_11_0_X

git clone git@github.com:greyson-newton/TrackingTools.git -b bugfix-make-cosmic-work-greysonnewton

git clone https://github.com/cms-mual/MuAlSupplementaryFiles.git -b CMSSW_10_1_X



bugfix-make-cosmic-work-greysonnewton

JSON:

cp /afs/cern.ch/cms/CAF/CMSCOMM/COMM_DQM/certification/Collisions18/13TeV/PromptReco/Cert_314472-316271_13TeV_PromptReco_Collisions18_JSON.txt .

GPR:

cp /afs/cern.ch/cms/CAF/CMSALCA/ALCA_MUONALIGN/www/muonGeometries/UL2018/data_DT-1100-111111_2018UL_IOV1_CMSSW106_JSON-313041-320377_dataRun2_MuAl_v1_01.db .

Edit Config File:

https://github.com/cms-mual/Alignment/commit/31c24cb68b5de20ed2bb90f3d4abd618a1556bbc

./createJobs.py data_DT-1100-110001_MuAlGlobalCosmics-06Jun2018-v1_2018A_ 1 \
data_DT-1100-111111_2018UL_IOV1_CMSSW106_JSON-313041-320377_dataRun2_MuAl_v1_01.db MuAlGlobalCosmics-06Jun2018-v1_2018A.py \
--inputInBlocks \
-s data_DT-1100-110001_MuAlGlobalCosmics-06Jun2018-v1_2018A.sh \
--validationLabel data_DT-1100-110001_MuAlGlobalCosmics-06Jun2018-v1_2018A \
--b --user_mail youremail --minTrackPt 30 --maxTrackPt 200 --maxDxy 0.2 \
--minNCrossedChambers 1 --residualsModel pureGaussian --peakNSigma 1.6 \
--station123params 110001 --station4params 100001 --cscparams 100001 --useResiduals 1100 \
--mapplots --curvatureplots --segdiffplots --extraPlots \
--globalTag 105X_dataRun2_v6 \
--createAlignNtuple --noCleanUp --noCSC \
--gprcdconnect sqlite_file:GPR_Aug03_2019_SW1060_GT106X_dataRun2_newTkAl_v18_IOV1_dL_iter2.db \
--gprcd IdealGeometry --is_Alca --T0 --iscosmics
