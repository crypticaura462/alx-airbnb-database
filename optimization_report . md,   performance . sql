
SELECT b.booking_id,
b.booking_date,
u.user_id,
u.name AS user_name,
u.email AS user_email,
p.property.id,
p.title AS property_title,
p.location AS property_location,
pay.payment_id,
pay.amount,
pay.status AS payment_status
    FROM bookings b
    JOIN users u ON b.user_id = u.user_id
    JOIN properties p ON b.property_id = p.property_id
    LEFT JOIN payments pay ON b.payment_id = pay.payment_id; 