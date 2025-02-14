from flask import Flask, request, jsonify

app = Flask(__name__)

@app.route('/')
def home():
    return "Server is running!"

@app.route('/pranto/', methods=['GET'])
def get_data():
    uid = request.args.get('uid')
    region = request.args.get('region')

    if not uid or not region:
        return jsonify({"error": "Missing parameters"}), 400

    visits = 22
    response_text = f"PLAYER GOT {visits} VISIT..CONTACT @ASIBHASANPRANTOO"
    
    return jsonify({"message": response_text})

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000)
