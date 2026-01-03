FOODS = {
    "ご飯": {"cal": 1.68, "protein": 0.025},
    "鶏むね肉": {"cal": 1.20, "protein": 0.23}
}

@app.route("/api/nutrition", methods=["POST"])
def nutrition():
    from flask import request
    data = request.json
    food = data["food"]
    grams = float(data["grams"])

    if food not in FOODS:
        return jsonify({"error": "不明な食材"}), 400

    result = {
        "calories": FOODS[food]["cal"] * grams,
        "protein": FOODS[food]["protein"] * grams
    }
    return jsonify(result)
