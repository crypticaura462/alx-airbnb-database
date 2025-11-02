# Performance Monitoring Report
## Query Analyze 
SELECT b.booking,u.name,p.title,pay.amount
FROM bookings b
JOIN users u ON b.user_id = u.user_id
JOIN properties p ON b.property_id=p.property_id
LEFT JOIN payments pay ON b.booking_id=pay.booking_id;
## Initial Performance(Before Optimization)
-Execution Time:340 ms
-EXPLAIN ANALYZE Result :Full table scan on bookings (Seq Scan )
## Bottlenecks Identified
-bookings.user_id had no index
-bookings.property_id had no