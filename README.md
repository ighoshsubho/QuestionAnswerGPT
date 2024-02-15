# How to go about and train on your data

## Install the dependencies

```python
pip install torch numpy transformers datasets tiktoken wandb tqdm
```

## Prepare train and validation splits

```python
cd data && python prepare.py
```

## Train the model

```python
python train.py config/train_go_book.py --device=mps --compile=False --eval_iters=20 --log_interval=1 --block_size=64 --batch_size=12 --n_layer=4 --n_head=4 --n_embd=128 --max_iters=2000 --lr_decay_iters=2000 --dropout=0.0
```

## Test it with sample.py

```python
python sample.py --out_dir=out_go_data --device=mps --start="Go"
```
