# ---------------------------------------------------------------
# 학생 과제: 아래 각 줄이 무엇을 하는지 주석으로 설명을 달아보세요.
# ---------------------------------------------------------------

FROM python:3.12-slim
# 이미지 베이스 설정

WORKDIR /app
# 작업 디렉토리를 /app으로 설정

COPY requirements.txt .
# 필요한 패키지 목록을 작업 디렉토리에 복사

RUN pip install --no-cache-dir -r requirements.txt
# 도커 이미지는 빌드 후 패키지 목록을 수정할 일이 적으므로 불필요한 캐시 파일 생성 막는 옵션 설정 후
# 파이썬 패키지 매니저를 통해 위에서 복사해둔 패키지 목록을 설치

COPY . .
# 현재 디렉토리의 내용을 작업 디렉토리로 복사

RUN useradd -m appuser
# 보안을 위해 루트 계정 말고 일반 사용자 계정을 생성

USER appuser
# 사용자 계정을 위에 만든 일반 계정으로 전환

ENV APP_TITLE="InhaTC DevOps실습 : 2-C 임태훈의 방명록" \
    THEME_COLOR="#FFE7B5"        
# 환경 변수 설정

EXPOSE 5000
# 도커가 사용할 포트 고지

CMD ["python", "app.py"]
# 컨테이너 실행 시 파이썬 환경의 app.py를 실행
