> LSTR: https://github.com/amazon-science/long-short-term-transformer <br>
> MAT: https://github.com/Echo0125/MAT-Memory-and-Anticipation-Transformer/tree/main <br>
> MiniROAD: https://github.com/jbistanbul/MiniROAD <br>
> CMeRT: https://github.com/pangzhan27/CMeRT <br>

## Training with MiniROAD style non-uniform loss
LSTR
```
cd LSTR
python tools/train_net.py --config_file configs/THUMOS/LSTR/lstr_long_512_work_8_kinetics_1x.yaml LOSS.NONUNIFORM True
```
MAT
```
cd MAT
python tools/train_net.py --config_file configs/THUMOS/MAT/lstr_long_512_work_8_kinetics_1x.yaml LOSS.NONUNIFORM True
# Applying weights to increase the proportion of short-memory results
python tools/train_net.py --config_file configs/THUMOS/MAT/lstr_long_512_work_8_kinetics_1x.yaml LOSS.NONUNIFORM True LOSS.DET_WEIGHT True
```
CMeRT
```
cd CMeRT
python main.py --config_file configs/THUMOS/cmert_long256_work4_kinetics_1x.yaml LOSS.NONUNIFORM True
# Applying weights to increase the proportion of short-memory results
python main.py --config_file configs/THUMOS/cmert_long256_work4_kinetics_1x.yaml LOSS.NONUNIFORM True LOSS.DET_WEIGHT True
```
MiniROAD
```
cd MiniROAD
# Uniform loss
python main.py --config configs/miniroad_thumos_kinetics_uniform.yaml
# Non-uniform loss
python main.py --config configs/miniroad_thumos_kinetics.yaml
```
