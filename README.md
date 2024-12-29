# Monolith_kamui
# 必要なツール
- Python 3.11+
- Node.js 20.10.0+
- Docker
- PostgreSQL 15.0
git clone https://github.com/your-org/monolith.git
cd monolith
python -m venv venv
source venv/bin/activate  # Windows: .\venv\Scripts\activate
pip install -r requirements.txt
cp .env.example .env
# .envファイルを編集して必要な環境変数を設定
alembic upgrade head
# バックエンド
uvicorn app.main:app --reload

# フロントエンド
cd frontend
npm install
npm run dev
SPOTIFY_CLIENT_ID=your_client_id
SPOTIFY_CLIENT_SECRET=your_client_secret
APPLE_MUSIC_KEY_ID=your_key_id
APPLE_MUSIC_TEAM_ID=your_team_id
APPLE_MUSIC_PRIVATE_KEY=your_private_key
AMAZON_MUSIC_ACCESS_KEY=your_access_key
AMAZON_MUSIC_SECRET_KEY=your_secret_key
# バックエンドテスト
pytest

# フロントエンドテスト
npm test
docker-compose up -d
kubectl apply -f k8s/
